---
title: cl.exe Dönüş Değeri
ms.date: 09/05/2018
helpviewer_keywords:
- cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
ms.openlocfilehash: 06e0993f6a96117ab73f22e73857843dfcc334a1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836731"
---
# <a name="return-value-of-clexe"></a>cl.exe Dönüş Değeri

cl.exe başarı durumunda (hatasız) sıfır, aksi halde sıfır olmayan değer döndürür.

cl.exe'nin dönüş değeri script, powershell, .cmd veya .bat dosyasından derleme yapıyorsanız kullanışlı olabilir. Hatalar ya da uyarılar olması durumunda, onları giderebilmeniz için, derleyicinin çıktısını yakalamanızı öneririz.

cl.exe'nin tamamı listelenemeyecek kadar çok olası hata çıkış kodu var. % ProgramFiles (x86)% \ Windows Kits \\ <em>sürümü</em>\ ınclude\shared\ dizinine Windows yazılım geliştirme seti 'nde bulunan winerror. h veya ntstatus. h dosyalarında bir hata kodu arayabilirsiniz. Ondalık olarak döndürülen hata kodları, arama için onaltılık olarak dönüştürülmelidir. Örneğin, -1073741620 hata kodu ondalık olarak dönüştürüldüğünde 0xC00000CC olur. Bu hata ntstatus.h dosyasında bulundu ve ilgili ileti "Belirtilen paylaşım adı uzak sunucuda bulunamıyor" şeklindedir. İndirilebilir bir Windows hata kodları listesi için bkz. [&#91;MS-ERREF&#93;: Windows hata kodları](/openspecs/windows_protocols/MS-ERREF).

Derleyici hata iletisinin anlamını bulmak için Visual Studio'da hata arama yardımcı programını da kullanabilirsiniz. Visual Studio komut kabuğu 'nda, yardımcı programı başlatmak için **errlook.exe** girin; Visual Studio IDE ' de, menü çubuğunda **Araçlar**, **hata arama**' yı seçin. Hatayla ilişkili açıklayıcı metni bulmak için hata değerini girin. Daha fazla bilgi için bkz. [ERRLOOK başvurusu](errlook-reference.md).

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

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
