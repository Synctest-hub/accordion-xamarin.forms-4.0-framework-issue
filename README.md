# How to overcome the crash Java.Lang.NullPointerException in Xamarin.Forms Accordion (SfAccordion)

In [SfAccordion](https://help.syncfusion.com/xamarin/accordion/getting-started?), When loading Label as direct children of [Header](https://help.syncfusion.com/cr/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Accordion.AccordionItem~Header.html?) or [Content](https://help.syncfusion.com/cr/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Accordion.AccordionItem~Content.html?) of [AccordionItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.Expander.XForms~Syncfusion.XForms.Accordion.AccordionItem.html?), then it will lead to exception in Xamarin.Forms 4.0 and above version.

However, the issue can be resolved in application level by loading Label inside Grid in **AccordionItem.Header** and **AccordionItem.Content**.

You can also refer the following article.

https://www.syncfusion.com/kb/11432/how-to-overcome-the-crash-java-lang-nullpointerexception-in-xamarin-forms-accordion

**XAML**

Loading Label inside **Header** and **Content** in Grid
``` xml
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Accordion;assembly=Syncfusion.Expander.XForms"
             x:Class="AccordionXamarin.MainPage" Padding="{OnPlatform iOS='0,40,0,0'}">
 
    <ContentPage.Content>
        <syncfusion:SfAccordion ExpandMode="MultipleOrNone" >
            <syncfusion:SfAccordion.Items>
                <syncfusion:AccordionItem>
                    <syncfusion:AccordionItem.Header>
                        <Grid>
                            <Label Text="Cheese burger" HeightRequest="50" VerticalTextAlignment="Center"/>
                        </Grid>
                    </syncfusion:AccordionItem.Header>
                    <syncfusion:AccordionItem.Content>
                        <Grid Padding="10" BackgroundColor="NavajoWhite">
                            <Label Text="Hamburger accompanied with melted cheese. The term itself is a portmanteau of the words cheese and hamburger. The cheese is usually sliced, then added a short time before the hamburger finishes cooking to allow it to melt." VerticalTextAlignment="Center"/>
                        </Grid>
                    </syncfusion:AccordionItem.Content>
                </syncfusion:AccordionItem>
                <syncfusion:AccordionItem>
                    <syncfusion:AccordionItem.Header>
                        <Grid>
                            <Label Text="Veggie burger" HeightRequest="50" VerticalTextAlignment="Center"/>
                        </Grid>
                    </syncfusion:AccordionItem.Header>
                    <syncfusion:AccordionItem.Content>
                        <Grid Padding="10" BackgroundColor="NavajoWhite">
                            <Label Text="Veggie burger, garden burger, or tofu burger uses a meat analogue, a meat substitute such as tofu, textured vegetable protein, seitan (wheat gluten), Quorn, beans, grains or an assortment of vegetables, which are ground up and formed into patties." VerticalTextAlignment="Center"/>
                        </Grid>
                    </syncfusion:AccordionItem.Content>
                </syncfusion:AccordionItem>
                ...
            </syncfusion:SfAccordion.Items>
        </syncfusion:SfAccordion>
    </ContentPage.Content>
</ContentPage>
```
