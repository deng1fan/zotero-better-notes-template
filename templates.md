# [Note] 论文阅读模板

<h1><span style="color: #467EEA;display: inline">
(${topItem.getField('date')}) ${topItem.getField('title')}
</span></h1>
<p></p>
<h1><span style="color: #EF89B1">动机</span></h1>
<p></p>
<p></p>
<h1><span style="color: #EF89B1">主要创新点</span></h1>
<p></p>
<p></p>
<h1><span style="color: #EF89B1">个人评价</span></h1>
<p></p>
<p></p>
<h1><span style="color: #EF89B1">相关工作</span></h1>
<p></p>
<p></p>
<h1><span style="color: #EF89B1">实验设置</span></h1>
<p></p>
<p></p>
<h1><span style="color: #EF89B1">结果讨论</span></h1>
<p></p>
<p></p>
<h1><span style="color: #EF89B1">一些细节</span></h1>
</div>

# [Item] 插入多条条目

<h2>${topItem.getField('title')}</h2>
<table>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">Title </p>
        </th>
        <td style="background-color:#dbeedd;">
            <p>${topItem.getField('title')}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#f3faf4;">
            <p style="text-align: right">${(()=>{
              if(topItem.itemType === "conferencePaper") return "Conference";
              if(topItem.itemType === "journalArticle") return "Journal";
              if(topItem.itemType === "report") return "Publisher";
              return "Publisher";})()}</p>
        </th>
        <td style="background-color:#f3faf4;"><p>${(()=>{
              if(topItem.itemType === "conferencePaper") {
                const res =  topItem.getField("conferenceName");
                return res?res:topItem.getField("proceedingsTitle");
              };
              if(topItem.itemType === "journalArticle") return topItem.getField("publicationTitle");
              if(topItem.itemType === "report") return topItem.getField("institution");
              return topItem.getField("publicationTitle");})()}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">Authors </p>
        </th>
        <td style="background-color:#dbeedd;">
            <p>${topItem.getCreators().map((v)=>v.firstName+" "+v.lastName).join("; ")}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#f3faf4;">
            <p style="text-align: right">Pub. date </p>
        </th>
        <td style="background-color:#f3faf4;">
            <p>${topItem.getField('date')}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">DOI </p>
        </th>
        <td style="background-color:#dbeedd;">
            <a href="https://doi.org/${topItem.getField('DOI')}">${topItem.getField('DOI')}</a>
        </td>
    </tr>
    <tr>
        <th style="background-color:#f3faf4;">
            <p style="text-align: right">URL</p>
        </th>
        <td style="background-color:#f3faf4;">
            <p>${topItem.getField('url')}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">CitationKey</p>
        </th>
        <td style="background-color:#dbeedd;">
            <p>${topItem.citationKey?topItem.citationKey:''}</p>
        </td>
    </tr>
</table>

# [Item] 插入多条条目以及相关笔记

<h2>${topItem.getField('title')}</h2>
<table>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">Title </p>
        </th>
        <td style="background-color:#dbeedd;">
            <p>${topItem.getField('title')}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#f3faf4;">
            <p style="text-align: right">${(()=>{
              if(topItem.itemType === "conferencePaper") return "Conference";
              if(topItem.itemType === "journalArticle") return "Journal";
              if(topItem.itemType === "report") return "Publisher";
              return "Publisher";})()}</p>
        </th>
        <td style="background-color:#f3faf4;"><p>${(()=>{
              if(topItem.itemType === "conferencePaper") {
                const res =  topItem.getField("conferenceName");
                return res?res:topItem.getField("proceedingsTitle");
              };
              if(topItem.itemType === "journalArticle") return topItem.getField("publicationTitle");
              if(topItem.itemType === "report") return topItem.getField("institution");
              return topItem.getField("publicationTitle");})()}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">Authors </p>
        </th>
        <td style="background-color:#dbeedd;">
            <p>${topItem.getCreators().map((v)=>v.firstName+" "+v.lastName).join("; ")}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#f3faf4;">
            <p style="text-align: right">Pub. date </p>
        </th>
        <td style="background-color:#f3faf4;">
            <p>${topItem.getField('date')}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">DOI </p>
        </th>
        <td style="background-color:#dbeedd;">
            <a href="https://doi.org/${topItem.getField('DOI')}">${topItem.getField('DOI')}</a>
        </td>
    </tr>
    <tr>
        <th style="background-color:#f3faf4;">
            <p style="text-align: right">URL</p>
        </th>
        <td style="background-color:#f3faf4;">
            <p>${topItem.getField('url')}</p>
        </td>
    </tr>
    <tr>
        <th style="background-color:#dbeedd;">
            <p style="text-align: right">CitationKey</p>
        </th>
        <td style="background-color:#dbeedd;">
            <p>${topItem.citationKey?topItem.citationKey:''}</p>
        </td>
    </tr>
</table>
${itemNotes.map((noteItem)=>{
const noteLine = `<h2  style="color:red; background-color: #efe3da;">📜 Note:  <a href="${Zotero.Knowledge4Zotero.knowledge.getNoteLink(noteItem)}" rel="noopener noreferrer nofollow">${noteItem.key}</a></h2>
<blockquote>
    ${noteItem.getNote()}
    <p style="background-color: pink;"><strong>Merge Date: </strong> ${new Date().toISOString().substr(0,10)+" "+ new Date().toTimeString()}</p>
</blockquote>
<p style="color:red; background-color: #efe3da;"><strong>📝 Comments</strong></p>
<blockquote>
    <p>Make your comments</p>
    <p></p>
</blockquote>`;
copyNoteImage(noteItem);
return noteLine;
}).join("\n")}

