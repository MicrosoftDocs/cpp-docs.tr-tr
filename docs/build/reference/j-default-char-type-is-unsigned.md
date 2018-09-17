---
title: -J (varsayılan karakter türü imzasız) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
dev_langs:
- C++
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 400985751d9ceebf7cc2c5f632cb33c5ba847bfe
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714291"
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

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Proje Özellikleriyle Çalışma](../../ide/working-with-project-properties.md)