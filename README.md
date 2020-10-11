# master-programs-file-
all in one for file handling and  hello world  for check configuration




Writing state information to a file
-----------------------------------





-------------------
	C
-------------------
#include<stdio.h>

int main()
{
    FILE *read;
    FILE *write;
    char *filename = "myfile.txt";
    read = fopen( filename, "r" );
    if( read == NULL )
    {
        //File doesn't exist. Have to write something
        write = fopen( filename, "w" );
        fprintf( write, "%s", "writesomethinghere" );
        fclose( write );
    }
    else
    {
        //File exists. Read data from the file
        char somedata[ 20 ];
        fscanf( read, "%s", somedata );
        printf( "%s", somedata );
        fclose( read );
    }
    return 0;
}



----------------------------------------------------------------------------


-------------------
	C++
-------------------

#include<iostream>
#include<fstream>
#include<string>

using namespace std;

int main()
{
    ifstream readfile;
    ofstream writefile;
    string filename = "myfile.txt";
    readfile.open( filename.c_str() );
    if( readfile )
    {
        //I can read something from the file
        readfile.close();
    }
    else
    {
        //The file doesn't exist
        writefile.open( filename.c_str() );
        //write something to the file
        writefile << " write some data " <&lt; endl;
        writefile.close();
    }
    return 0;
}



----------------------------------------------------------------------------


-------------------
	java
-------------------

import java.io.*;
import java.lang.*;

public class Solution
{
    public static void main( String[] args )
    {
        File fileName = new File( "myfile.txt" );
        if( !fileName.exists() )
        {
            System.out.println( "this file doesn't exist " );
            try
            {
                fileName.createNewFile();
                FileWriter fileWrite = new FileWriter( fileName );
                BufferedWriter bufferedWriter = new BufferedWriter( fileWrite );
                //bufferedWriter.write( "write something here " );
                bufferedWriter.close();
            } catch ( IOException e )
            {
                //catch exception
            }
        }
        else
        {
            //System.out.println( "this file exists " );
            try
            {
                byte[] buffer = new byte[ 100 ];
                FileInputStream inputStream  = new FileInputStream( fileName );
                int readLines = -1;
                while( ( readLines = inputStream.read( buffer ) ) != -1 )
                {
                    //System.out.println( new String( buffer ) );
                }
                inputStream.close();
            } catch ( IOException e )
            {
                //catch exception
            }
        }
    }
}

----------------------------------------------------------------------------



-------------------
	CSHARP
-------------------
using System;
using System.IO;


public class Solution
{
    public static void Main( )
    {
        string fileName = "myfile.txt";
        FileStream file = new FileStream( fileName, FileMode.OpenOrCreate, FileAccess.Read );
        StreamReader sr = new StreamReader( file );
        string s = sr.ReadToEnd();
        if( string.IsNullOrEmpty( s ) )
        {
            file.Close();
            //The file is empty. Write something to it
            //Console.WriteLine( "file doesn't exist " );
            file = new FileStream( fileName, FileMode.OpenOrCreate, FileAccess.Write );
            StreamWriter sw = new StreamWriter( file );
            sw.Write( "Write something here " );
            sw.Close();
        }
        else
        {
            //Console.WriteLine( s );
        }
    }
}



----------------------------------------------------------------------------



-------------------
	PYTHON
-------------------

#!/usr/bin/python

filename = "myfile.txt"
with open( filename ) as f:
    # file read can happen here
    # print "file exists"
    print f.readlines()

with open( filename, "w") as f:
    # print "file write happening here"
    f.write("write something here ")



----------------------------------------------------------------------------



-------------------
	RUBY
-------------------
#!/usr/bin/env ruby

filename = "myfile.txt"
if File.exist?( filename )
    #puts "file read happening"
    f = File.open(filename, 'r')
    data = f.read
    puts data
end

f = File.open(filename, 'a+')
#puts "file write happening"
f.puts "write something here"



----------------------------------------------------------------------------



-------------------
	PERL
-------------------

#!/usr/bin/env perl

$filename = "myfile.txt";

if( -e $filename )
{
    unless(open FILE, $filename)
    {
        die "Cannot open file";
    }

    while(my $line = <FILE>)
    {
        print $line;
    }

    close FILE;
}
unless(open FILE, '>>'.$filename)
{
    die "Cannot open file";
}
print FILE "Write something here";
close FILE;





----------------------------------------------------------------------------

----------------------------------------------------------------------------

----------------------------------------------------------------------------





SAMPLE INPUT 
5



SAMPLE OUTUT

 hello world 
 hello world 
 hello world 
 hello world 
 hello world





-------------------
	C
-------------------
#include <stdio.h>
int main() {
    int i, n;
    scanf("%d", &n);
    for (i=0; i<n; i++) {
        printf("hello world\n");
    }
    return 0;
}




----------------------------------------------------------------------------




-------------------
	C++
-------------------

#include <iostream>
using namespace std;
int main() {
    int i, n;
    cin >> n;
    for (i=0; i<n; i++) {
        cout << "hello world\n";
    }
    return 0;
}




----------------------------------------------------------------------------




-------------------
	C#
-------------------
using System;
namespace Solution {
    class Solution {
        static void Main(string[] args) {
            var line1 = System.Console.ReadLine().Trim();
            var N = Int32.Parse(line1);
            for (var i = 0; i < N; i++) {
                System.Console.WriteLine("hello world");
            }
        }
    }
}




----------------------------------------------------------------------------



-------------------
	JAVA
-------------------
import java.io.*;
public class Solution {
    public static void main(String args[] ) throws Exception {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String line = br.readLine();
        int N = Integer.parseInt(line);
        for (int i = 0; i < N; i++) {
            System.out.println("hello world");
        }
    }
}





----------------------------------------------------------------------------



-------------------
	OBJECTIVE C
-------------------
#import<Foundation/Foundation.h>

int main(int argc, const char* argv[])
{
    @autoreleasepool {
        NSInteger n;
        scanf("%lu", &n);

        for (NSInteger i = 0; i < n; i++) {
            /*
             * Do not use NSLog to print to stdout
             */
            printf("hello world\n");
        }

        return 0;
    }
}






----------------------------------------------------------------------------




-------------------
	JAVASCRIPT
-------------------
function processData(input) {
    var i;
    for (i = 0; i < parseInt(input); i++) {
        console.log("hello world");
    }
}

process.stdin.resume();
process.stdin.setEncoding("ascii");
_input = "";
process.stdin.on("data", function (input) {
    _input += input;
});

process.stdin.on("end", function () {
   processData(_input);
});




----------------------------------------------------------------------------


-------------------
	PYTHON
-------------------
N = int(raw_input())
for i in xrange(N):
    print "hello world"



----------------------------------------------------------------------------



-------------------
	RUBY
-------------------
N = gets
1.step(N.to_i, 1) { |i| print "hello world\n" }


----------------------------------------------------------------------------



-------------------
	PHP
-------------------
<?php
fscanf(STDIN, "%d\n", $number);

for ( $i = 0; $i < $number; $i++) {
    echo "hello world\n";
}



----------------------------------------------------------------------------



-------------------
	LUA
-------------------
N = io.read ()
for i = 1, tonumber(N), 1 do
    print("hello world")
end


----------------------------------------------------------------------------





-------------------
 COMMON LISP(SBCL)
-------------------
(let ((n (parse-integer (read-line))))
    (dotimes (i n)
        (format t "hello world~%")))



----------------------------------------------------------------------------



-------------------
	ERLANG
-------------------
-module(solution).
-export([main/0]).

main() ->
    {ok, [Num]} = io:fread("", "~d"),
    print_hello(Num).

print_hello(0) ->
    0;
print_hello(N) ->
    io:format("Hello World~n"),
    print_hello(N - 1).






----------------------------------------------------------------------------





-------------------
	GO
-------------------


package main

import (
    "fmt"
)

func main() {
    times := readInt()
    for i := 0; i < times; i++ {
        fmt.Println("hello world")
    }
}

func readInt() int {
    var n int
    _, err := fmt.Scanf("%d", &n)

    if err != nil {
        panic(err)
    }

    return n
}








----------------------------------------------------------------------------



-------------------
	CLOJURE
-------------------

(let [n (Integer/parseInt (read-line))]
  (dotimes [_ n]
      (println "hello world")))





----------------------------------------------------------------------------



-------------------
	R
-------------------
f <- file("stdin")
on.exit(close(f))

T <- readLines(f)
T <- strsplit(T, " ")
Ti <- as.numeric(T[[1]])

for(i in 1:Ti){
    write("hello world", stdout())
}






----------------------------------------------------------------------------



-------------------
	SWIFT
-------------------
import Foundation

let n = Int(readLine()!)!

for i in 1...n {
    print("hello world")
}


---------------------------------------------------------------------------
