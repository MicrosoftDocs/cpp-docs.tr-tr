---
description: 'Daha fazla bilgi edinin: grafik Işlemleri (C++/CLı)'
title: Grafik İşlemleri (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- GDI+ [C++]
- .NET Framework [C++], graphics
- images [C++], .NET Framework and
- GDI+ [C++], about graphics operations
- graphics [C++], .NET Framework and
- GDI+ [C++], displaying images
- graphics [C++], displaying images
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
- GDI+ [C++], rotating images
- graphics [C++], rotating images
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: bba27228-b9b3-4c9c-b31c-a04b76702a95
ms.openlocfilehash: 84dbc75aa306219b8733848ece5c594ca40a0489
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223548"
---
# <a name="graphics-operations-ccli"></a>Grafik İşlemleri (C++/CLI)

Windows SDK kullanarak görüntü işlemesini gösterir.

Aşağıdaki konularda, <xref:System.Drawing.Image?displayProperty=fullName> görüntü işleme gerçekleştirmek için sınıfının kullanımı gösterilmektedir.

## <a name="display-images-with-the-net-framework"></a><a name="display"></a> .NET Framework görüntüleri görüntüleme

Aşağıdaki kod örneği, <xref:System.Drawing.Graphics> ana form için nesnesine bir işaretçi almak üzere OnPaint olay işleyicisini değiştirir. <xref:System.Windows.Forms.Form.OnPaint%2A>İşlevi, büyük olasılıkla bir Visual Studio uygulama sihirbazıyla oluşturulmuş bir Windows Forms uygulamasına yöneliktir.

Görüntü sınıfı tarafından temsil edilir <xref:System.Drawing.Image> . Görüntü verileri, yöntemi kullanılarak bir. jpg dosyasından yüklenir <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> . Görüntü forma çizilmeden önce, form görüntüye sığacak şekilde yeniden boyutlandırılır. Görüntü çizimi <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> yöntemiyle gerçekleştirilir.

<xref:System.Drawing.Graphics>Ve <xref:System.Drawing.Image> sınıflarının ikisi de <xref:System.Drawing?displayProperty=fullName> ad alanıdır.

### <a name="example"></a>Örnek

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override
{
    Graphics^ g = pe->Graphics;
    Image^ image = Image::FromFile("SampleImage.jpg");
    Form::ClientSize = image->Size;
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );
}
```

## <a name="draw-shapes-with-the-net-framework"></a><a name="draw"></a> .NET Framework şekil çizme

Aşağıdaki kod örneği, <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.Form.OnPaint%2A> <xref:System.Drawing.Graphics> ana form için nesnesine bir işaretçi almak üzere olay işleyicisini değiştirmek için sınıfını kullanır. Bu işaretçi daha sonra formun arka plan rengini ayarlamak ve ve yöntemlerini kullanarak bir çizgi ve yay çizmek için kullanılır <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> <xref:System.Drawing.Graphics.DrawArc%2A> .

### <a name="example"></a>Örnek

```cpp
#using <system.drawing.dll>
using namespace System;
using namespace System::Drawing;
// ...
protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override
{
   Graphics^ g = pe->Graphics;
   g->Clear(Color::AntiqueWhite);

   Rectangle rect = Form::ClientRectangle;
   Rectangle smallRect;
   smallRect.X = rect.X + rect.Width / 4;
   smallRect.Y = rect.Y + rect.Height / 4;
   smallRect.Width = rect.Width / 2;
   smallRect.Height = rect.Height / 2;

   Pen^ redPen = gcnew Pen(Color::Red);
   redPen->Width = 4;
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);

   Pen^ bluePen = gcnew Pen(Color::Blue);
   bluePen->Width = 10;
   g->DrawArc( bluePen, smallRect, 90, 270 );
}
```

## <a name="rotate-images-with-the-net-framework"></a><a name="rotate"></a> .NET Framework görüntüleri döndürme

Aşağıdaki kod örneği, <xref:System.Drawing.Image?displayProperty=fullName> bir görüntüyü diskten yüklemek için sınıfının kullanımını gösterir, 90 derece döndürün ve yeni bir. jpg dosyası olarak kaydeder.

### <a name="example"></a>Örnek

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );
   image->Save("SampleImage_rotated.jpg");
   return 0;
}
```

## <a name="convert-image-file-formats-with-the-net-framework"></a><a name="convert"></a> Resim dosyası biçimlerini .NET Framework Dönüştür

Aşağıdaki kod örneği, <xref:System.Drawing.Image?displayProperty=fullName> <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> görüntü dosyalarını dönüştürmek ve kaydetmek için kullanılan sınıfı ve sabit listesini gösterir. Aşağıdaki kod bir. jpg dosyasından bir görüntü yükler ve ardından. gif ve. bmp dosya biçimlerinde kaydeder.

### <a name="example"></a>Örnek

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;
using namespace System::Drawing::Imaging;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->Save("SampleImage.png", ImageFormat::Png);
   image->Save("SampleImage.bmp", ImageFormat::Bmp);

   return 0;
}
```

## <a name="related-sections"></a>İlgili Bölümler

[Grafik Programlamaya Başlarken](/dotnet/framework/winforms/advanced/getting-started-with-graphics-programming)

[GDI+ Yönetilen Kodu Hakkında](/dotnet/framework/winforms/advanced/about-gdi-managed-code)

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>
