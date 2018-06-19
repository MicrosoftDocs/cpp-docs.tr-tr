---
title: _outp, _outpw, _outpd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _outpd
- _outp
- _outpw
apilocation:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- _outpw
- _outpd
- _outp
- outpd
dev_langs:
- C++
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 140b53fd90d393f2629dda6573d994635b96f417
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391515"
---
# <a name="outp-outpw-outpd"></a>_outp, _outpw, _outpd
Bir bağlantı noktası, bir bayt çıkışları (`_outp`), bir sözcük (`_outpw`), veya bir çift sözcük (`_outpd`).  
  
> [!IMPORTANT]
>  Bu işlevler artık kullanılmıyor. Visual Studio 2015'te başlayarak, bunlar CRT kullanılabilir değildir.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _outp(  
unsigned short port,  
int databyte   
);  
unsigned short _outpw(  
unsigned short port,  
unsigned short dataword   
);  
unsigned long _outpd(  
unsigned short port,  
unsigned long dataword   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Bağlantı noktası*  
 Bağlantı noktası numarası.  
  
 *databyte, dataword*  
 Çıkış değerleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlevler, veri çıkışı döndürür. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 `_outp`, `_outpw`, Ve `_outpd` işlevler yazma byte, bir sözcük ve bir çift sözcük sırasıyla belirtilen çıkış bağlantı noktasına. *Bağlantı noktası* bağımsız değişkeni, herhangi bir işaretsiz tamsayı 0 - 65.535; aralığında olabilir *databyte* aralık 0 - 255; herhangi bir tamsayı ve *dataword* herhangi bir değer bir tamsayı, imzasız kısa tamsayı ve imzasız uzun tamsayı aralığında sırasıyla olabilir.  
  
 Bu işlevlerin bir g/ç bağlantı noktasına doğrudan yazma çünkü kullanıcı kodunda kullanılamaz. Bu işletim sistemlerindeki g/ç bağlantı noktaları hakkında daha fazla bilgi için MSDN'de "Seri iletişimler, Win32 için" arayın.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_outp`|\<conio.h >|  
|`_outpw`|\<conio.h >|  
|`_outpd`|\<conio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)   
 [_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)