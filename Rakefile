# Thanks to Lincoln Mullen
# https://github.com/lmullen/historybib

task :default => [:sort, :keys]

desc "Sort the BibTeX file"
task :sort do 
  sh "bibtool -s -i master.bib -o master.bib"
  sh "bibtool -r bibtool-rsc/crossref.rsc -i master.bib -o master.bib"
  sh "bibtool -r bibtool-rsc/fix-page-range.rsc -i master.bib -o master.bib"
end

desc "Generate the citation keys file"
task :keys do
  sh "bibkeys -s master.bib > citekeys.txt"
end

desc "Commit and push repository"
task :push do
  sh "git add master.bib"
  sh "git commit -m 'Updated bib'"
  sh "git push origin master"
end
