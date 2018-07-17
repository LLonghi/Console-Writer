Arrumar mais tarde

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace RichConsoleWriter
{
    public static class ConsoleWriter
    {
        public static readonly object ConsoleWriterLock = new object();

        public static void Write(string text, ConsoleColor color = ConsoleColor.White)
        {
            Console.ForegroundColor = color;
            Console.Write(text);
            BackToWhite();
        }

        public static void WriteLine(string text, ConsoleColor color = ConsoleColor.White, bool printTimeLog = true)
        {
            if (printTimeLog)
                TimeLog();
            Console.ForegroundColor = color;
            Console.WriteLine(text);
            BackToWhite();
        }

        public static void NewLine()
        {
            Console.WriteLine("");
        }

        private static void TimeLog()
        {
            Console.ForegroundColor = ConsoleColor.DarkGray;
            Console.Write($"[{DateTime.Now}]");
            BackToWhite();
        }

        private static void BackToWhite()
        {
            Console.ForegroundColor = ConsoleColor.White;
        }
    }
}

