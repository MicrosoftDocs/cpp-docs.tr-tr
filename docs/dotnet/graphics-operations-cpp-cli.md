---
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
ms.openlocfilehash: dd27fc603454d18f30fb367399e0ee18be74015e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505436"
---
# <a name="graphics-operations-ccli"></a>Grafik İşlemleri (C++/CLI)

Görüntü işleme Windows SDK'sını kullanarak gösterir.

Aşağıdaki konular kullanımını gösteren <xref:System.Drawing.Image?displayProperty=fullName> görüntü işleme gerçekleştirmek için sınıf.

## <a name="display"></a> .NET Framework ile görüntüleri görüntüleme

OnPaint olay işleyicisi, bir işaretçi almak için aşağıdaki kod örneği değiştirir <xref:System.Drawing.Graphics> ana formu için nesne. <xref:System.Windows.Forms.Form.OnPaint%2A> İşlevi, büyük olasılıkla bir Visual Studio Uygulama Sihirbazı'yla oluşturulmuş bir Windows Forms uygulaması için tasarlanmıştır.

Görüntü tarafından temsil edilen <xref:System.Drawing.Image> sınıfı. Görüntü verilerini kullanarak bir .jpg dosya yüklendikten <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> yöntemi. Forma resmi çizilmeden önce formun resmi içine alması için yeniden boyutlandırılır. Çizimi görüntü ile gerçekleştirilen <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> yöntemi.

<xref:System.Drawing.Graphics> Ve <xref:System.Drawing.Image> sınıflardır hem de <xref:System.Drawing?displayProperty=fullName> ad alanı.

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

## <a name="draw"></a> .NET Framework ile şekil çizme

Aşağıdaki kod örneğinde <xref:System.Drawing.Graphics> değiştirmek için sınıf <xref:System.Windows.Forms.Form.OnPaint%2A> işaretçisi almak için olay işleyicisini <xref:System.Drawing.Graphics> ana formu için nesne. This işaretçisi ardından form arka plan rengini ayarlamak ve bir satır ve kullanarak bir yay çizmek için kullanılan <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> ve <xref:System.Drawing.Graphics.DrawArc%2A> yöntemleri.

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

## <a name="rotate"></a> .NET Framework ile görüntüleri döndürme

Aşağıdaki kod örneği, kullanımını gösterir <xref:System.Drawing.Image?displayProperty=fullName> sınıfı bir görüntüyü diskten yükleme, 90 derece döndür ve yeni bir .jpg dosya olarak kaydedin.

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

## <a name="convert"></a> .NET Framework ile görüntü dosyası biçimlerini dönüştürme

Aşağıdaki kod örneğinde <xref:System.Drawing.Image?displayProperty=fullName> sınıfı ve <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> dönüştürmek ve görüntü dosyaları kaydetmek için kullanılan sabit listesi. Aşağıdaki kod bir .jpg dosyasından görüntüyü yükler ve sonra .gif ve .bmp dosya biçimlerinde kaydeder.

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

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>
