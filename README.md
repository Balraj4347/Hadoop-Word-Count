# Hadoop-Word-Count
Implemented a word count application using the MapReduce programming model in apache Hadoop stand-alone Mode.

WordCount is a simple program which counts the number of occurrences of each
word in a given text input data set. WordCount fits very well with the
MapReduce programming model making it a great example to understand the
Hadoop Map/Reduce programming style.

Our implementation consists of two main parts:
1. Mapper
2. Reducer 


A Mapper overrides the --map function from the Class
org.apache.hadoop.mapreduce.Mapper" which provides pairs as the input. A Mapper
implementation may output pairs using the provided Context .
Input value of the WordCount Map task will be a line of text from the input data file
and the key would be the line number <line_number, line_of_text> .
Map task outputs <word, one> for each word in the line of text.

        void Map (key, value)
        {
        for each word x in value:
        output.collect(x,1);
        }
        
        
A Reducer collects the intermediate <key,value> output from multiple map
tasks and assemble a single result.
Here, the WordCount program will sum up the occurrence of each word to
pairs as <word, occurrence>.

      void Reduce (keyword, <list of value>)
        { foreach x in <list of value>:
        sum+=x;
        final_output.collect(keyword, sum);
        }
        
  

