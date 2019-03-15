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
ms.openlocfilehash: ed296d339949814dbd796bb5d8e23a406be71c69
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814169"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (Varsayılan Karakter Türü İmzasız)

Varsayılan değişiklikleri `char` türünü `signed char` için `unsigned char`ve `char` türü sıfır genişletilmiş için genişletildiğinde bir `int` türü.

## <a name="syntax"></a>Sözdizimi

```
/J
```

## <a name="remarks"></a>Açıklamalar

Varsa bir `char` değeri olarak bildirilen açıkça `signed`, **/J** seçeneği bunu etkilemez ve değer için genişletildiğinde işaret genişletilmiş bir `int` türü.

**/J** seçeneği tanımlar `_CHAR_UNSIGNED`, birlikte kullanılan `#ifndef` varsayılan aralığını tanımlamak için Lımıts.h dosyasındaki `char` türü.

ANSI C ve C++ özel uygulanışı gerektirmez `char` türü. Bu seçenek, sonunda İngilizce dışında bir dil çevrileceğini karakter verileriyle çalışırken yararlıdır.

> [!NOTE]
>  ATL/MFC ile Bu derleyici seçeneğini kullanırsanız, bir hata oluşturulabilir. Tanımlayarak bu hatayı devre dışı bırakılamadı rağmen `_ATL_ALLOW_CHAR_UNSIGNED`, bu geçici çözüm desteklenmez ve her zaman çalışmayabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.

1. Projedeki **özellik sayfaları** iletişim kutusunda, sol bölmede altında **yapılandırma özellikleri**, genişletme **C/C++** seçip **komutsatırı**.

1. İçinde **ek seçenekler** bölmesinde belirtin **/J** derleyici seçeneği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[C++ derleyicisi ayarlayın ve derleme Visual Studio özellikleri](../working-with-project-properties.md)
