<%*
let title = tp.file.title;
if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("请输入笔记标题");
    if (title != null && title != "") {
         await tp.file.rename(title);
    } else {
        title = tp.file.title;
    }
}
let slug = title.toLowerCase()
    .replace(/\s+/g, "-")
    .replace(/[^\w\-\u4e00-\u9fa5]/g, "");
tR += "Title: " + title + "\n";
tR += "Date: " + tp.file.creation_date("YYYY-MM-DD HH:mm") + "\n";
tR += "Slug: " + slug + "\n";
tR += "Category: life\n";
tR += "Status: published\n";
tR += "\n";
%>
