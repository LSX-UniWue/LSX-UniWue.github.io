---
layout: default
---

# Chair of Data Science at JMU Wuerzburg

This page is an overview of research projects by the [Data Science chair](https://www.informatik.uni-wuerzburg.de/datascience/home/) at the Julius-Maximilians-University Wuerzburg.
Our research topics include Natural Language Processing, Recommender Systems and Deep Learning for Dynamical Systems.

Our organization is currently present at:
* Github: [LSX-UniWue](https://www.github.com/LSX-UniWue)
* Twitter: [datascience_jmu](https://twitter.com/datascience_jmu)

## Projects

<div id="projects-list"></div>

<script>
  const projects = document.getElementById("projects-list");
  
  let htmlString = "";
  fetch("https://api.github.com/users/LSX-UniWue/repos").then(data => data.json()).then(json => {
    // sort array based on name of repo
    json.sort((a, b) => a.name.toLowerCase() > b.name.toLowerCase() ? 1 : -1);

    // create string
    for(let repo of json){
      if(repo.name == "LSX-UniWue.github.io"){
        continue
      }
  
      htmlString += "<h3><a href='" + repo.html_url + "'>" + repo.name + "</a></h3><p>" + repo.description + "</p>";
    }

    // update html
    projects.innerHTML = htmlString;
  });
</script>
