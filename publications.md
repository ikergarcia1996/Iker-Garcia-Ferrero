---
title: Iker García-Ferrero
button_title: Publications
layout: default
filename: publications
---

# Publications

---
### <img src="https://github.com/hitz-zentroa/GoLLIE/blob/main/assets/GoLLIE.png?raw=true" width="25"> GoLLIE: Annotation Guidelines improve Zero-Shot Information-Extraction
Oscar Sainz, <ins>Iker García-Ferrero</ins>, Rodrigo Agerri, Oier Lopez de Lacalle, German Rigau and Eneko Agirre  
ArXiv 2023  
📖[Paper](https://arxiv.org/abs/2310.03668) 📒[Code](https://github.com/hitz-zentroa/GoLLIE/)

---

### This is not a Dataset: A Large Negation Benchmark to Challenge Large Language Models
<ins>Iker García-Ferrero</ins>, Begoña Altuna, Javier Alvez, Itziar Gonzalez-Dios, German Rigau  
EMNLP 2023    
📖[Paper](https://arxiv.org/abs/2310.15941) 📒[Code](https://github.com/hitz-zentroa/This-is-not-a-Dataset)

---

### T-Projection: High Quality Annotation Projection for Sequence Labeling Tasks
<ins>Iker García-Ferrero</ins> , Rodrigo Agerri, German Rigau  
Findings of the EMNLP 2023  
📖[Paper](https://arxiv.org/abs/2212.10548) 📒[Code](https://github.com/ikergarcia1996/T-Projection)  

---

### NLP Evaluation in trouble: On the Need to Measure LLM Data Contamination for each Benchmark
Oscar Sainz, Jon Ander Campos, <ins>Iker García-Ferrero</ins> , Julen Etxaniz, Oier Lopez de Lacalle, Eneko Agirre  
Findings of the EMNLP 2023    
📖[Paper](https://arxiv.org/pdf/2310.18018v1.pdf) 📒[Code](https://hitz-zentroa.github.io/lm-contamination/)  

---

### IXA/Cogcomp at SemEval-2023 Task 2: Context-enriched Multilingual Named Entity Recognition using Knowledge Bases
<ins>Iker García-Ferrero</ins>, Jon Ander Campos, Oscar Sainz, Ander Salaberria, Dan Roth  
SemEval 2023  
📖[Paper](https://aclanthology.org/2023.semeval-1.186/) 📒[Code](https://github.com/ikergarcia1996/Context-enriched-NER)

---

### HiTZ@ Antidote: Argumentation-driven Explainable Artificial Intelligence for Digital Medicine
Rodrigo Agerri, Iñigo Alonso, Aitziber Atutxa, Ander Berrondo, Ainara Estarrona, <ins>Iker García-Ferrero</ins>, Iakes Goenaga, Koldo Gojenola, Maite Oronoz, Igor Perez-Tejedor, German Rigau, Anar Yeginbergenova  
SEPLN 2023: 39th International Conference of the Spanish Society for Natural Language Processing  
📖[Paper](https://arxiv.org/abs/2306.06029)


---

### Model Transfer or Data Transfer? Cross-Lingual Sequence Labelling in Zero-Resource Settings 
<ins>Iker García-Ferrero</ins> , Rodrigo Agerri, German Rigau  
Findings of the EMNLP 2022  
📖[Paper](https://aclanthology.org/2022.findings-emnlp.478/) 📒[Code](https://github.com/ikergarcia1996/Easy-Label-Projection)

---

### Benchmarking Meta-embeddings: What Works and What Does Not 
<ins>Iker García-Ferrero</ins> , Rodrigo Agerri, German Rigau  
Findings of the EMNLP 2021  
📖[Paper](https://aclanthology.org/2021.findings-emnlp.333) 📒[Code](https://github.com/ikergarcia1996/MetaVec)

---

### A Common Semantic Space for Monolingual and Cross-Lingual Meta-Embeddings
<ins>Iker García-Ferrero</ins> , Rodrigo Agerri, German Rigau   
ArXiv 2020  
📖[Paper](https://arxiv.org/abs/2001.06381) 📒[Code](https://github.com/ikergarcia1996/MVM-Embeddings)

---

<div class="publications px-4 p-5" id="publications">
    <h2 class="pb-2 border-bottom">Publications</h2>
    <ul id="publication-list">
    </ul>
</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-ENjdO4Dr2bkBIFxQpeoTz1HIcje39Wm4jDKdf19U8gI4ddQ3GYNS7NTKfAdVQSZe"
        crossorigin="anonymous"></script>

<script>
        //Get the button
        let back_to_top_btn = document.getElementById("btn-back-to-top");

        // When the user scrolls down 20px from the top of the document, show the button
        window.onscroll = function () {
            scrollFunction();
        };

        function scrollFunction() {
            if (
                document.body.scrollTop > 20 ||
                document.documentElement.scrollTop > 20
            ) {
                back_to_top_btn.style.display = "block";
            } else {
                back_to_top_btn.style.display = "none";
            }
        }
        // When the user clicks on the button, scroll to the top of the document
        back_to_top_btn.addEventListener("click", backToTop);

        function backToTop() {
            document.body.scrollTop = 0;
            document.documentElement.scrollTop = 0;
        }

        // Copy to clipboard function
        function copy_to_clipboard(copyText) {
            // Copy the text inside the text field
            navigator.clipboard.writeText(copyText);

            // Alert the copied text
            alert("Copied the text: " + unescape(copyText));
        }

        // Load publications
        var xhttp = new XMLHttpRequest();
        xhttp.responseType = 'json';
        xhttp.onreadystatechange = function () {
            if (this.readyState == 4 && this.status == 200) {
                publications_data = xhttp.response.data;

                publications_data.sort(function (a, b) { return b.citationCount - a.citationCount });
                console.log(publications_data);

                let pub_html = document.getElementById("publication-list")
                for (publication of publications_data) {
                    // pub_html.innerHTML += "<li>";
                    pub_html.innerHTML += '<li class="py-2"><a href="' + publication.url + '" style="text-decoration: none">' + publication.title + '</a>';
                    let authors = "";
                    for (author of publication.authors) {
                        if (author.name != "Oscar Sainz") {
                            authors += author.name + ", ";
                        } else {
                            authors += "<u>" + author.name + "</u>, ";
                        }

                    }
                    authors = authors.slice(0, -2);
                    pub_html.innerHTML += '<b>Authors</b>: ' + authors + '<br>';
                    console.log(authors);
                    pub_html.innerHTML += '<span class="badge border-dark text-dark rounded-pill"><img width="15" height="15" src="assets/img/quote-svgrepo-com.svg"/>' + publication.citationCount + "</span>";
                    pub_html.innerHTML += '<span class="badge border-dark text-dark rounded-pill"><img width="15" height="15" src="assets/img/date-range-svgrepo-com.svg"/> ' + publication.year + "</span>";
                    pub_html.innerHTML += '<span class="badge border-dark text-dark rounded-pill"><img width="15" height="15" src="assets/img/book-svgrepo-com.svg"/> ' + publication.venue + "</span>";
                    pub_html.innerHTML += '<span class="badge border-dark text-dark rounded-pill"> <a onclick="copy_to_clipboard(\'' + escape(publication.citationStyles["bibtex"]) + '\')">BibTex</a></span>';
                    // pub_html.innerHTML += '<small> <b>Year</b>: ' + publication.year + ' | <b>Venue</b>: ' + publication.venue + '<br></small>';
                    pub_html.innerHTML += "</li>";
                }
            }
        };
        xhttp.open("GET", "https://api.semanticscholar.org/graph/v1/author/1724648481/papers?fields=url,title,year,authors,citationCount,venue,citationStyles", true);
        xhttp.send();
    </script>