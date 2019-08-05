# Bachelor of Science <!-- omit in toc -->

This repository was used for my bachelor thesis to graduate as Bachelor of Science in Business Informatics - (Core Process Engineering & Digital Management).

The thesis was written using LateX with a MiKTeX installation on Windows and Visual Studio Code as text editor.

This project is based on [this respository](https://github.com/skyfrk/dhbw-vs-latex-template) and has been adjusted to my specific needs.

**Table of Contents**
- [TODO-List](#todo-list)
- [Setup](#setup)
- [Structure](#structure)
  - [Project structure](#project-structure)
- [Sections (Verzeichnisse)](#sections-verzeichnisse)
  - [Abkürzungsverzeichnis](#abkürzungsverzeichnis)
  - [Abbildungsverzeichnis](#abbildungsverzeichnis)
- [Snippets](#snippets)
- [License](#license)

## TODO-List

- [x] Korrekte Formatierung (o: 2,5cm, u: 2.0cm, l: 4.0cm, r: 1,5cm)
- [x] Kopfzeile Abstand 1,25cm
- [x] Fußzeile Abstand 1,25cm
- [x] Schrift Arial, 12pt
- [x] Abstand vor Absätzen 6pt
- [x] Zeilenabstand 1,5
- [x] Blocksatz
- [x] Einheitliche Überschriften Formatierung
- [x] Korrekte Römische und Arabische Seitennummerrierung


## Setup

1. [Setup](#Prerequisites) your writing environment.
1. [Download](https://github.com/florianloechle\dhbw-vs-latex) and extract this template. If you are using git you can use `git clone` instead.
2. Open the downloaded folder with your editor of choice.
3. Customize `Konfiguration.tex` to your needs.
4. Write your sections in `Content`. (actually optional, write them whereever you want)
5. Compile your work. The final pdf file will be in the same directory as the `Main.tex` file.

## Structure

### Project structure

* **./Abbildungen**
  * Images, etc.. save them here.

* **./Ads**
  * Files like Appendix, non-disclosure-agreement etc... Customize them to your need. Or don't.
  * Ads/**Appendix.tex**
    * Self explanatory.
  * Ads/**Praeambel.tex**
    * Praeambel of the document, loading packages.. setting stuff up. You should no need to change this.
* **./Content**
  * Your thesis content could go here.
* **./Settings**
  * Your thesis content could go here.
  * Settings/**dhbw-bibstyle.tex**
    * Loads custom DHBW bibliography style.
  * Settings/**dhbw-citestyle.tex**
    * Loads custom DHBW citing style.
  * Settings/**acronymns.tex**
    * Place your acronymns here.
* **Main.pdf**
  * This is the final output file.
* **Main.tex**
  * This is the main .tex file which glues all parts together.

## Sections (Verzeichnisse)

### Abkürzungsverzeichnis

Abkürzungen (acronymns) können unter *Settings*/*acronymns*.*tex* bearbeitet und erweitert werden.

### Abbildungsverzeichnis

Wird automatisch aktualisert wenn deine Abbildung eingefügt wird.
Vorraussetzung ist das die Abbildung mit einem caption und einem label begleitet wird.

## Snippets

**Empty Page**

```tex
\newpage
\pagestyle{empty}
```

**Cite direct**
````tex
\glqq /* Text */ \glqq{}\myfootcite[42 <- /*Side number */]{hitchhiker}
````
**Cite indirect**
````tex
/* Text */ \myfootcite[Vgl.][42 <- /*Side number */]{hitchhiker}
````

**Insert Image**
```tex
% include image
\begin{figure}[ht] % ht means that the figure should appear at this exact position
\centering
\caption{Interesting caption}
\includegraphics[width=\textwidth]{bechtle.jpg} % put your pictures into ./figures/
\caption*{\footnotesize{\textbf{Quelle:} \cite[]{Anderie2018}}}
\label{fig:goodreference} % add a reference label
\end{figure}

% refer to a figure
Lorem ipsum dolor sit amet \autoref{fig:goodreference} consetetur sadipscing elitr.
% will resolve to:
% Lorem ipsum dolor sit amet figure 1 consetetur sadipscing elitr.
```

**Aufzählungen mit Punkt**
````tex
\begin{itemize}
\item erstes Stichwort
\item zweites Stichwort
\end{itemize}
````

**Insert Wrapping Image**
```tex
\begin{wrapfigure}{r}{0.6\textwidth}
	\begin{center}
		\includegraphics[width=0.25\textwidth]{abbildungen/bechtle.jpg}
		\caption[Test Figure]{Eine Grafik ohne Sinn \\ \textbf{Quelle:} Eigene Darstellung}
	\end{center}
\end{wrapfigure}
```

**Conditional**
```tex
\newif\sperrvermerk
\ifsperrvermerk .... \else ... \fi
\sperrvermerktrue
\sperrvermerkfalse
```

**Acronyme**
```tex
\ac{Kuerzel} Bei der ersten Verwendung von ac{Kuerzel} wird die Langfassung der Abkürzung und die Abkürzung selbst in Klammern dargestellt. Wird der Befehl ac{Kuerzel} das nächste mal aufgerufen erschneit nur nocht die Abkürzung.
\acresetall	Der Befehl \acresetall ermöglicht es das Gedächnis des ac Befehls zu löschen. Wird der Befehl \acresetall gesetzt verhält sich der ac Befehl danach wie beim ersten Aufruf (Bei allen bisher gesetzten Abkürzungen).
\acf{Kuerzel}	Mit acf{Kuerzel} gibt es ein zweites Erstes Mal für diese Abkürzung. Das heißt, sie wird wieder in \der Langform und der geklammerten Abkürzung gezeigt.
\acs{Kuerzel}	acs{Kuerzel} gibt nur die Abkürzung aus.
\acl{Kuerzel}	acl{Kuerzel} gibt nur die Langform der Abkürzung aus.
\acp{Kuerzel}	Gleiche Wirkung wie ac{Kuerzel} nur hier wird der Plural ausgegeben.
\acfp{Kuerzel}	Gleiche Wirkung wie acf{Kuerzel} nur hier wird der Plural ausgegeben.
\acsp{Kuerzel}	Gleiche Wirkung wie acs{Kuerzel} nur hier wird der Plural ausgegeben.
\aclp{Kuerzel}	Gleiche Wirkung wie acl{Kuerzel} nur hier wird der Plural ausgegeben.
\acfi{Kuerzel}	Die Langform wird kursiv geschrieben, während die Abkürzung mit Kapitälchen dargestellt wird.
\iac{Kuerzel}	Hier wird der Abkürzung (beziehungsweise wenn es das erste Mal ist der Langform mit geklammerter Abkürzung) der unbestimmte englische Artikel a voran gestellt.
\Iac{Kuerzel}	Hier wird der Abkürzung (beziehungsweise wenn es das erste Mal ist der Langform mit geklammerter Abkürzung) der unbestimmte englische Artikel A voran gestellt.
\acused{Kuerzel}	Die Abkürzung wird als gesetzt markiert (gleiche Wirkung wie der ac Befehl) aber nicht angezeigt. Danach zeigt der ac Befehl nur noch die Abkürzung an.
\acsu{Kuerzel}	Zeigt die Abkürzung an und markiert sie als gesetzt.
\aclu{Kuerzel}	Zeigt die Langform an und markiert sie als gesetzt.
```

**Code Examples**
```tex
\begin{figure}[ht] % ht means that the figure should appear at this exact position
\centering
\caption{My Code Example}
\begin{lstlisting}[language=Javascript]
	Name.prototype = {
		methodName: function(params){
			var doubleQuoteString = "some text";
			var singleQuoteString = 'some more text';
			// this is a comment
			if(this.confirmed != null && typeof(this.confirmed) == Boolean && this.confirmed == true){
				document.createElement('h3');
				$('#system').append("This looks great");
				return false;
			} else {
				throw new Error;
			}
		}
	}
\end{lstlisting}
% \caption*{\footnotesize{\textbf{Quelle:} \cite[]{Anderie2018}}}
\label{fig:code1} % add a reference label
\end{figure}

```

## License

**MIT**



