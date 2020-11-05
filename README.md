Mein Code:

SpecFlowFfeature1Steps.cs

*****

using System;
using TechTalk.SpecFlow;
using Xunit;

namespace Test
{
    [Binding]
    public class SpecFlowFeature1Steps
    {
        double radian;
        double result;
        
        [Given(@"the radian is Pi")]
        public void GivenTheRadianIsPi()
        {
            radian = Math.PI;
        }
        
        [When(@"the sine key is pressed")]
        public void WhenTheSineKeyIsPressed()
        {
            result = Math.Sin(radian);
        }
        
        [When(@"the cosine key is pressed")]
        public void WhenTheCosineKeyIsPressed()
        {
            result = Math.Cos(radian);
        }
        
        [When(@"the tangens key is pressed")]
        public void WhenTheTangensKeyIsPressed()
        {
            result = Math.Tan(radian);
        }
        
        [Then(@"the result should be (.*)")]
        public void ThenTheResultShouldBe(double p0)
        {
            var expected = p0;
            var actual = result;
            Assert.Equal(expected, actual, 5);
        }
    }
}

SpecFlowFeature1.feature

***

Feature: SpecFlowFeature1
	In order to avoid silly mistakes
	As a math idiot
	I want to be told the results of trigonometric calculations

@mytag
Scenario: calculate sine
	Given the radian is Pi
	When the sine key is pressed
	Then the result should be 0

Scenario: calculate cosine
    Given the radian is Pi
	When the cosine key is pressed
	Then the result should be -1

Scenario: calculate tangens
    Given the radian is Pi
	When the tangens key is pressed
	Then the result should be 0
