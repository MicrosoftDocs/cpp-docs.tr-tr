---
title: Cl.exe dönüş değeri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: dc8b5deab86597aca6e35b3d6f2d1adcca18be69
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374599"
---
# <a name="return-value-of-clexe"></a>cl.exe Dönüş Değeri
cl.exe başarı durumunda (hatasız) sıfır, aksi halde sıfır olmayan değer döndürür.  
  
 cl.exe'nin dönüş değeri script, powershell, .cmd veya .bat dosyasından derleme yapıyorsanız kullanışlı olabilir. Hatalar ya da uyarılar olması durumunda, onları giderebilmeniz için, derleyicinin çıktısını yakalamanızı öneririz.  
  
 cl.exe'nin tamamı listelenemeyecek kadar çok olası hata çıkış kodu var. Bir hata kodunu Winerror.h'de arayabilir ya da ntstatus.h dosyaları dahil Windows Yazılım Geliştirme Seti % ProgramFiles (x86) %\Windows Setleri\\`version`\Include\shared\ dizini. Ondalık olarak döndürülen hata kodları, arama için onaltılık olarak dönüştürülmelidir. Örneğin, -1073741620 hata kodu ondalık olarak dönüştürüldüğünde 0xC00000CC olur. Bu hata ntstatus.h dosyasında bulundu ve ilgili ileti "Belirtilen paylaşım adı uzak sunucuda bulunamıyor" şeklindedir. Windows hata kodları indirilebilir bir listesi için bkz [ &#91;MS-ERREF&#93;: Windows hata kodları](http://msdn.microsoft.com/library/cc231196).  
  
 Derleyici hata iletisinin anlamını bulmak için Visual Studio'da hata arama yardımcı programını da kullanabilirsiniz. Visual Studio komut kabuğunda girin **errlook.exe** ; yardımcı programını başlatın veya menü çubuğunda, Visual Studio IDE içinde seçmek için **Araçları**, **hata arama**. Hatayla ilişkili açıklayıcı metni bulmak için hata değerini girin. Daha fazla bilgi için bkz: [ERRLOOK başvurusu](../../build/reference/errlook-reference.md).  
  
## <a name="remarks"></a>Açıklamalar  
 cl.exe'nin dönüş değerini kullanan örnek bir .bat dosyası aşağıdadır.  
  
```  
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