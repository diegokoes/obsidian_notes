<%*
// Untitled notes (Ctrl+N) get a proper prefix_topic name first
let title = tp.file.title;
if (/^Untitled( \d+)?$/.test(title)) {
    const name = await tp.system.prompt("Note name (prefix_topic)");
    if (name) {
        title = name.trim().toLowerCase().replace(/\s+/g, "_");
        await tp.file.rename(title);
    }
}

// Parent = hub named like the prefix (java_streams -> java), else the domain folder's hub
const parts = title.split("_");
const prefix = parts.length > 1 ? parts[0] : null;
const topFolder = tp.file.folder(true).replace(/^\/+/, "").split("/")[0].toLowerCase();
let up = "";
if (prefix && tp.file.find_tfile(prefix)) {
    up = prefix;
} else if (topFolder && topFolder !== title) {
    up = topFolder;
}

const crumb = (prefix ? [prefix, parts.slice(1).join(" ")] : [title])
    .map(s => s.toUpperCase())
    .join(" > ");

if (up) {
    tR += `---\nup:\n  - "[[${up}]]"\n---\n`;
}
tR += `# ${crumb}\n`;
-%>
<% tp.file.cursor() %>
