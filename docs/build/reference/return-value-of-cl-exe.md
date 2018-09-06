---
title: Cl.exe dönüş değeri | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4baca82dd9cf4581a5e20a7c426f4d79e383f3c
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894674"
---
# <a name="return-value-of-clexe"></a>cl.exe Dönüş Değeri

cl.exe başarı durumunda (hatasız) sıfır, aksi halde sıfır olmayan değer döndürür.

cl.exe'nin dönüş değeri script, powershell, .cmd veya .bat dosyasından derleme yapıyorsanız kullanışlı olabilir. Hatalar ya da uyarılar olması durumunda, onları giderebilmeniz için, derleyicinin çıktısını yakalamanızı öneririz.

cl.exe'nin tamamı listelenemeyecek kadar çok olası hata çıkış kodu var. Bir hata kodu arayabilir veya ntstatus.h dosyalarından % ProgramFiles (x86) %\Windows Windows Yazılım Geliştirme Seti de Setleri\\<em>sürüm</em>\Include\shared\ dizin. Ondalık olarak döndürülen hata kodları, arama için onaltılık olarak dönüştürülmelidir. Örneğin, -1073741620 hata kodu ondalık olarak dönüştürüldüğünde 0xC00000CC olur. Bu hata ntstatus.h dosyasında bulundu ve ilgili ileti "Belirtilen paylaşım adı uzak sunucuda bulunamıyor" şeklindedir. Windows hata kodlarının indirilebilir listesi için bkz: [ &#91;MS-ERREF&#93;: Windows hata kodlarının](https://msdn.microsoft.com/library/cc231196).

Derleyici hata iletisinin anlamını bulmak için Visual Studio'da hata arama yardımcı programını da kullanabilirsiniz. Visual Studio komut kabuğunda girin **errlook.exe** yardımcı programı veya Visual Studio IDE'de menü çubuğunda, seçmek için **Araçları**, **hata arama**. Hatayla ilişkili açıklayıcı metni bulmak için hata değerini girin. Daha fazla bilgi için [ERRLOOK başvurusu](../../build/reference/errlook-reference.md).

## <a name="remarks"></a>Açıklamalar

cl.exe'nin dönüş değerini kullanan örnek bir .bat dosyası aşağıdadır.

```cmd
echo off
cl /W4 t.cpp
@if ERRORLEVEL == 0 (
   goto good
)

@if ERRORLEVEL != 0 (
   goto bad
)

:good
   echo "clean compile"
   echo %ERRORLEVEL%
   goto end

:bad
   echo "error or warning"
   echo %ERRORLEVEL%
   goto end

:end
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)