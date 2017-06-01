# URL-cutting
Cut the URL from a xml file


open(XML,'sitemap.xml');

open(OUT, '+>output.txt');

$xml_hdr=<XML>;

$data=<XML>;

$pos=0;

print "Processing: $xml_hdr\n";

while ($pos > -1)

  { $pos=index($data,'<loc>');

##print "TEST Pt #L1: ", length($data), " : ",$pos,"\n";

    if ($pos < 0)

      {last;}

    $data=substr($data, $pos+5);

    $pos2=index($data, '</loc>');

    $output=substr($data, 0, $pos2);

    $data=substr($data, $pos2+6);
    
    $pos3 = index($data, 'usa');
    $data = substr($data,0,$pos3);
    $add = ".myshoptify";
    $data = $data. $add;
    $data   
##    print $output, "\r\n";

  }



close(XML);

close(OUT);



exit;
