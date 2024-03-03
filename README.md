# ÔN TẬP KIỂM TRA GIỮA KỲ - WPF

Tài liệu ôn tập kiểm tra giữa kỳ môn Xây dựng ứng dụng Windows - Phần WPF

## Sử dụng một số control thường dùng

### `Grid`

```xml
<Grid>
    <!-- Định nghĩa số cột cho lưới - grid -->
    <Grid.ColumnDefinitions>
        <ColumnDefinition />
        <ColumnDefinition Width="3*" /> <!-- Cột có độ rộng (Width) gấp 3 lần -->
        <ColumnDefinition />
        <ColumnDefinition />
    </Grid.ColumnDefinitions>

    <!-- Định nghĩa số dòng cho lưới - grid -->
    <Grid.RowDefinitions>
        <RowDefinition />
        <RowDefinition />
        <RowDefinition />
        <RowDefinition />
    </Grid.RowDefinitions>
</Grid>
```

Để phân bổ các control khác, sử dụng `Grid.Row` và `Grid.Column` với giá trị là chỉ số dòng và chỉ số cột bắt đầu tính từ `0`:

```xml
<TextBlock Grid.Row="0" Grid.Column="1" Text="Số hoá đơn"  />
<TextBlock Grid.Row="1" Grid.Column="1" Text="Ngày lập" />
<TextBlock Grid.Row="2" Grid.Column="1" Text="Tên khách hàng" />
<TextBlock Grid.Row="3" Grid.Column="1" Text="Tổng tiền" />
```

### `DataGrid`

```xml
<DataGrid AutoGenerateColumns="False">
    <DataGrid.Columns>
        <DataGridTextColumn Header="Mã hàng" />
        <DataGridTextColumn Header="Tên hàng" />
        <DataGridTextColumn Header="Đơn vị tính" />
        <DataGridTextColumn Header="Đơn gia" />
        <DataGridTextColumn Header="Số lượng" />
        <DataGridTextColumn Header="Thành tiền" />
        <DataGridTemplateColumn>
            <DataGridTemplateColumn.CellTemplate>
                <DataTemplate>
                    <Button Content="Xoá" x:Name="btnXoa" />
                </DataTemplate>
            </DataGridTemplateColumn.CellTemplate>
        </DataGridTemplateColumn>
    </DataGrid.Columns>
</DataGrid>
```

Nếu có một cột (column) không phải text, sử dụng `<DataGridTemplateColumn>`:

```xml
<DataGrid AutoGenerateColumns="False">
    <DataGrid.Columns>
        ...
        <DataGridTemplateColumn>
            <DataGridTemplateColumn.CellTemplate>
                <DataTemplate>
                    <Button />
                </DataTemplate>
            </DataGridTemplateColumn.CellTemplate>
        </DataGridTemplateColumn>
        ...
    </DataGrid.Columns>
</DataGrid>
```

- Thêm expander cho dòng:

```xml
<DataGrid AutoGenerateColumns="False">
    <DataGrid.Columns>
        ...
    </DataGrid.Columns>

    <DataGrid.RowDetailsTemplate>
        <DataTemplate>
            <Expander>
                ...
            </Expander>
        </DataTemplate>
    </DataGrid.RowDetailsTemplate>
</DataGrid>
```


