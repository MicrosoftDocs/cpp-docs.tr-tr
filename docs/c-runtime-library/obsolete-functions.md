---
title: "İşlevleri geçersiz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_wctype
- _loaddll
- _unloaddll
- _getdllprocaddr
- _seterrormode
- _beep
- _sleep
- _getsystime
- corecrt_wctype/is_wctype
- process/_loaddll
- process/_unloaddll
- process/_getdllprocaddr
- stdlib/_seterrormode
- stdlib/_beep
- stdlib/_sleep
- time/_getsystime
- time/_setsystime
dev_langs: C++
helpviewer_keywords:
- obsolete functions
- _beep function
- _sleep function
- _seterrormode function
ms.assetid: 8e14c2d4-1481-4240-8586-47eb43db02b0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8a8811703234f2c4e23dab6ad2b99b1aae316c04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="obsolete-functions"></a>Artık kullanılmayan işlevleri
Belirli kitaplık işlevleri geçersizdir ve daha yeni eşdeğerleri. Bu güncelleştirilmiş sürümleri için değiştirme öneririz. Artık kullanılmayan diğer işlevleri CRT kaldırıldı. Bu konu, kullanılmayan olarak kullanım dışı işlevler ve belirli bir Visual Studio sürümünde kaldırılmıştır işlevleri listeler.  
  
## <a name="deprecated-as-obsolete-in-visual-studio-2015"></a>Visual Studio 2015'te eski olarak kullanım dışı  
  
|Artık kullanılmayan işlevi|Alternatifi|  
|-----------------------|-----------------|  
|`is_wctype`|[iswctype](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|  
|`_loaddll`|[LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187), [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?LinkID=236091), veya [LoadPackagedLibrary](https://msdn.microsoft.com/library/windows/desktop/hh447159\(v=vs.85\).aspx)|  
|`_unloaddll`|[FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)|  
|`_getdllprocaddr`|[GetProcAddress](../build/getprocaddress.md)|  
|`_seterrormode`|[SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkID=255242)|  
|`_beep`|[Bip](https://msdn.microsoft.com/library/windows/desktop/ms679277\(v=vs.85\).aspx)|  
|`_sleep`|[Uyku](https://msdn.microsoft.com/library/windows/desktop/ms686298\(v=vs.85\).aspx)|  
|`_getsystime`|[GetLocalTime](https://msdn.microsoft.com/library/windows/desktop/ms724338\(v=vs.85\).aspx)|  
|`_setsystime`|[SetLocalTime](https://msdn.microsoft.com/library/windows/desktop/ms724936\(v=vs.85\).aspx)|  
  
## <a name="removed-from-the-crt-in-visual-studio-2015"></a>Visual Studio 2015'te CRT kaldırıldı  
  
|Artık kullanılmayan işlevi|Alternatifi|  
|-----------------------|-----------------|  
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md)|[_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|  
|[_getws alır](../c-runtime-library/gets-getws.md)|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|  
|[_get_output_format](../c-runtime-library/get-output-format.md)|Yok.|  
|[_heapadd](../c-runtime-library/heapadd.md)|Yok.|  
|[_heapset](../c-runtime-library/heapset.md)|Yok.|  
|[inp, inpw](../c-runtime-library/inp-inpw.md)|Yok.|  
|[_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)|Yok.|  
|[outp, outpw](../c-runtime-library/outp-outpw.md)|Yok.|  
|[_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)|Yok.|  
|[_set_output_format](../c-runtime-library/set-output-format.md)|Yok.|  
  
## <a name="removed-from-the-crt-in-earlier-versions-of-visual-studio"></a>Visual Studio'nun önceki sürümlerindeki CRT kaldırıldı  
 [_Lock'ı](../c-runtime-library/lock.md)  
  
 [_unlock](../c-runtime-library/unlock.md)