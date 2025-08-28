# How to show empty message when listview has no items in xamarin forms
This example demonstrates to show empty message when listview has no items by using the visibility property.

## Sample

```xaml
<Grid Padding="{OnPlatform iOS='0,40,0,0'}">
    <Grid.RowDefinitions>
        <RowDefinition Height="50"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Button x:Name="ItemSource" Grid.Row="0" 
            Text="Change ItemSource" 
            HorizontalOptions="CenterAndExpand"
            VerticalOptions="CenterAndExpand" 
            Command="{Binding OnItemsSourceChanged}"/>
    <Grid IsVisible="{Binding IsVisible}" Grid.Row="1">
        <Label x:Name="label"
                Text = "No Items :(" 
                FontSize ="Default"
                HorizontalOptions = "FillAndExpand"
                HorizontalTextAlignment = "Center"
                VerticalTextAlignment = "Center"
                VerticalOptions = "FillAndExpand"/>
    </Grid>
    <syncfusion:SfListView x:Name="listView" Grid.Row="1"  ItemsSource="{Binding ContactsInfo}"
                        IsVisible="{Binding Path=IsVisible, Converter={StaticResource visibilityConverter}}"
                        ItemSpacing="2" ItemSize="30">
        <syncfusion:SfListView.ItemTemplate>
            <DataTemplate>
                <Label Text="{Binding ContactName}"/>
            </DataTemplate>
        </syncfusion:SfListView.ItemTemplate>
    </syncfusion:SfListView>
</Grid>
```

See [How to show empty message when listview has no items in Xamarin.Forms](https://www.syncfusion.com/kb/9956/how-to-show-empty-message-when-listview-has-no-items-in-xamarin-forms) for more details.
## <a name="requirements-to-run-the-demo"></a>Requirements to run the demo ##

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/) or [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/).
* Xamarin add-ons for Visual Studio (available via the Visual Studio installer).

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.