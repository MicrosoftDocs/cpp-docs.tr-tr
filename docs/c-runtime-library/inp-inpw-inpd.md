---
title: _inp, _inpw, _inpd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _inp
- _inpw
- _inpd
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
dev_langs: C++
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 983efc1f3341ca334415e8cdd37f96f12fbb3e11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="inp-inpw-inpd"></a>_inp, _inpw, _inpd
Bir bayt bir bağlantı noktasından girişleri (`_inp`), bir sözcük (`_inpw`), veya bir çift sözcük (`_inpd`).  
  
> [!IMPORTANT]
>  Bu işlevler artık kullanılmıyor. Visual Studio 2015'te başlayarak, bunlar CRT kullanılabilir değildir.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _inp(   
   unsigned short port   
);  
unsigned short _inpw(   
   unsigned short port   
);  
unsigned long _inpd(   
   unsigned short port   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `port`  
 G/ç bağlantı noktası numarası.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Word, bayt işlevler döndürür veya çift word okuma `port`. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 `_inp`, `_inpw`, Ve `_inpd` işlevleri okuma byte, bir sözcük ve bir çift sözcük sırasıyla, belirtilen giriş bağlantı noktasından. Giriş değeri 0 - 65.535 aralığında imzasız herhangi kısa tamsayı olabilir.  
  
 Bu işlevler doğrudan bir g/ç bağlantı noktasından okuma çünkü bunlar kullanıcı kodu Windows NT, Windows 2000, Windows XP ve Windows Server 2003 kullanılmayabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_inp`|\<conio.h >|  
|`_inpw`|\<conio.h >|  
|`_inpd`|\<conio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)   
 [_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)