---
title: /J (Varsayılan Karakter Türü İmzasız)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
ms.openlocfilehash: 7bcf0f2eb2bef08757250999d0a6696b256fb15c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322192"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (Varsayılan Karakter Türü İmzasız)

`char` Varsayılan `signed char` türü `unsigned char`,'den 'e değiştirir ve `char` tür bir `int` türe genişletildiğinde sıfır uzatılır.

## <a name="syntax"></a>Sözdizimi

```
/J
```

## <a name="remarks"></a>Açıklamalar

Bir `char` değer açıkça olarak `signed`beyan edilirse , **/J** seçeneği onu etkilemez ve bir `int` türe genişletildiğinde değer imzaya uzatılır.

**/J** `_CHAR_UNSIGNED`seçeneği, varsayılan `#ifndef` `char` türün aralığını tanımlamak için LIMITS.h dosyasında kullanılan

ANSI C ve C++ `char` türünün belirli bir uygulamasını gerektirmez. Bu seçenek, sonunda İngilizce dışında bir dile çevrilecek karakter verileriyle çalışırken yararlıdır.

> [!NOTE]
> Bu derleyici seçeneğini ATL/MFC ile kullanırsanız, bir hata oluşturulabilir. Bu hatayı tanımlayarak `_ATL_ALLOW_CHAR_UNSIGNED`devre dışı kalsanız da, bu geçici çözüm desteklenmez ve her zaman çalışmayabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. **Çözüm Gezgini'nde,** proje için kısayol menüsünü açın ve ardından **Özellikler'i**seçin.

1. Proje **Özellik Sayfaları** iletişim kutusunda, **Configuration Properties**altında sol bölmede, **C/C++** genişletin ve ardından **Komut Satırı'nı**seçin.

1. Ek **Seçenekler** bölmesinde **/J** derleyicisi seçeneğini belirtin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](../working-with-project-properties.md)
