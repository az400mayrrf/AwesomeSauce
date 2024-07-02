# Awesome Sauce
using Xunit;
using System.IO;

namespace AwesomeSauceTests
{
    public class ReadmeTests
    {
        [Fact]
        public void ReadmeIsSpelledRight()
        {
            string readmePath = Path.Combine(Directory.GetCurrentDirectory(), "readme.md");
            Assert.True(File.Exists(readmePath), "Readme.md file does not exist.");

            string readmeContent = File.ReadAllText(readmePath);
            Assert.Contains("Awesome Sauce", readmeContent, StringComparison.OrdinalIgnoreCase);
        }
    }
}