---
description: Şu konuda daha fazla bilgi edinin:/J (varsayılan karakter türü imzasız)
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
ms.openlocfilehash: 0e6f09a05925fd0248f1e777d578570cd7b44946
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191231"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (Varsayılan Karakter Türü İmzasız)

Varsayılan **`char`** türü ' dan ' a değiştirir ve tür, **`signed char`** **`unsigned char`** **`char`** iletildiklerinde olduğunda tür sıfır genişletilir **`int`** .

## <a name="syntax"></a>Syntax

```
/J
```

## <a name="remarks"></a>Açıklamalar

Bir **`char`** değer açıkça olarak bildirilirse **`signed`** , **/j** seçeneği bunu etkilemez ve bir türe iletildiklerinde olduğunda bu değer imza genişletilir **`int`** .

**/J** seçeneği `_CHAR_UNSIGNED` , `#ifndef` varsayılan TÜRÜN aralığını tanımlamak için limit. h dosyasında ile birlikte kullanılan öğesini tanımlar **`char`** .

ANSI C ve C++, türü için belirli bir uygulama gerektirmez **`char`** . Bu seçenek, sonunda Ingilizce dışındaki bir dile çevrilecek karakter verileriyle çalışırken yararlıdır.

> [!NOTE]
> Bu derleyici seçeneğini ATL/MFC ile birlikte kullanıyorsanız bir hata oluşturulabilir. Bu hatayı tanımlayarak devre dışı bırakabilseniz de `_ATL_ALLOW_CHAR_UNSIGNED` , bu geçici çözüm desteklenmez ve her zaman çalışmayabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. **Çözüm Gezgini**' de, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. Proje **Özellik sayfaları** iletişim kutusundaki sol bölmede, **yapılandırma özellikleri** altında **C/C++** öğesini genişletin ve ardından **komut satırı**' nı seçin.

1. **Ek seçenekler** bölmesinde **/j** derleyici seçeneğini belirtin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](../working-with-project-properties.md)
