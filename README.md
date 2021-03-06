# UpCASE
**Up**load | **C**orrect | **A**nnotate | **S**earch | **E**xport 

UpCASE is a web application for building and maintaining language resources. It provides a wide range of options for viewing, evaluating, manipulating and enriching text collections. UpCASE is conceived as a multifunctional webapp where users can upload plain text, pdf or scanned texts whose characters are automatically recognized (OCR). While being able to search over the uploaded text, users can correct, annotate and export it into different formats.

### Background
UpCASE is the result of years of work with Romansh texts and lexical resources. In a number of earlier projects we have developed a web-based editing environment for collaborative OCR correction ([DRC](http://www.crestomazia.ch), [github](https://github.com/spinfo/drc)), a tool for collaborative annotation ([ARC](http://www.spinfo.phil-fak.uni-koeln.de/forschung-arc.html), [github](https://github.com/spinfo/arc)), and a framework for collaborative lexicon creation and maintenance ([maalr](http://www.spinfo.phil-fak.uni-koeln.de/maalr.html), [github](https://github.com/spinfo/maalr-core)). UpCASE comprises the experiences of these projects and combines the key features of collaborative corpus construction, enrichment and maintenance. Based on UpCASE, we started to build a collection of Romansh texts ([Biblioteca Digitala](http://www.biblioteca-digitala.ch)). UpCASE is still work in progress, for a showcase app see http://upcase.biblioteca-digitala.ch.   

![Biblioteca Digitala](https://cloud.githubusercontent.com/assets/161970/12014933/1c20c34a-ad35-11e5-8390-1025879fa934.png)


### Motivation 
Romansh is the smallest of the four national languages of Switzerland. With approx. 50.000 native speakers Romansh is considered an endangered language. Our interest is to show the relevance of using tools like UpCASE for other small languages having little or no support by official institutions: While in the first place UpCASE was developed for a specific historical text collection, namely the Romansh Chrestomathy compiled by Caspar Decurtins (1888-1919), the concepts and features can be transposed to other text collections and can be seen as an approach for preserving the cultural heritage of minority and endangered languages.

### Implementation Details
UpCASE is based on several state-of-the-art web technologies such as Spring WebMVC, Spring Data, JAXB, and JQuery. Using robust and scalable software on server side and lightweight, clean and interactive components on client side, UpCASE offers several options to treat text collections for searching, statistics, exporting, or to modify the data at hand, e.g. to edit, annotate or enrich. The data is persisted in MongoDB, whose records are structurally similar to JSON objects. The use of JSON enables a straightforward communication with other (language) resources, using predefined REST (Representational State Transfer) interfaces. 

### Functionality/Views
+ Uploaded text is indexed with Lucene and made accessible through an editable directory tree and a full text search. 

![UpCASE search view](https://cloud.githubusercontent.com/assets/161970/12014936/286629ce-ad35-11e5-8b0c-6cc2495047b0.png)

+ The stats view offers some basic statistical information about the text collection or selected parts of it. 
+ In the export view, the user can choose different formats, e.g. plaintext, TEI or HTML, to export the whole collection or parts of it.

![UpCASE export formats](https://cloud.githubusercontent.com/assets/161970/12014937/2cbc792e-ad35-11e5-9987-98d392546a16.png)

+ The edit view allows the user to modify the text, e.g. to correct errors or typos produced after the OCR process. The view contains both the editable word form and the relevant part of the scanned image with its highlighted position.

![UpCASE edit view](https://cloud.githubusercontent.com/assets/161970/12014951/598dbeae-ad35-11e5-96fc-3d310ca25cf3.png)

+ The annotation view allows the user to create annotations like POS-tags on the fly that are indexed and thus allowing complex searches on the search view. 
+ Finally, in the translation view we make use of a separate resource, the [Pledari Grond](http://www.pledarigrond.ch), an online dictionary for Romansh that we have developed in collaboration with the Lia Rumantscha an basis of our [maalr](https://github.com/spinfo/maalr-core)-framework.

###Quickstart

UpCASE is a [Maven](http://maven.apache.org/) based Java project developed within the [Eclipse IDE](https://www.eclipse.org/).

After downloading the code import the project into your Eclipse workspace. Make sure you have the [M2Eclipse](https://www.eclipse.org/m2e/) plugin installed. To run the application you may simply execute the [upcase.launch](https://github.com/spinfo/upcase/blob/master/upcase.launch) file by right clicking the file > Run As > m2 upcase… or if you are used to Maven you also may run the application from command line: e.g. ```mvn clean install jetty:run```

The compiled .war file will be deployed into the embedded jetty web server. Open the URL [http://localhost:8080/](http://localhost:8080/) in your browser (JavaScript has to be enabled). 

