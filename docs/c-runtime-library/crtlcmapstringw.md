---
title: __crtLCMapStringW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __crtLCMapStringW
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __crtLCMapStringW
dev_langs:
- C++
helpviewer_keywords:
- __crtLCMapStringW
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 261fb23c96bee0d646f64d587d9f7afecc59d4d2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="crtlcmapstringw"></a>__crtLCMapStringW
Bir karakter dizesi başka belirtilen yerel ayara bağımlı dönüştürme gerçekleştirme eşler. Bu işlev, giriş dizesi için bir sıralama anahtarı oluşturmak için de kullanılabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
int __crtLCMapStringW(  
   LCID    Locale,  
   DWORD   dwMapFlags,  
   LPCWSTR lpSrcStr,  
   int     cchSrc,  
   LPWSTR  lpDestStr,  
   int     cchDest)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Locale`  
 Yerel ayar tanımlayıcısı. Yerel ayar dize eşleştirme veya sıralama anahtarı oluşturma için bir bağlam sağlar. Bir uygulamanın kullanabileceği `MAKELCID` makrosu yerel ayar tanımlayıcısı oluşturun.  
  
 `dwMapFlags`  
 Dize eşleme veya sıralama anahtarı oluşturma sırasında kullanılacak dönüştürme türü.  
  
 `lpSrcStr`  
 İşlev eşlemeleri veya sıralama anahtarı oluşturma için kullanan bir kaynak dizesi işaretçi. Bu parametre bir UNICODE dizesi olduğu varsayılır.  
  
 `cchSrc`  
 Gösterdiği dizenin karakter cinsinden boyutu `lpSrcStr` parametresi. Bu sayı NULL Sonlandırıcı içerebilir veya eklemeniz gerekmez.  
  
 A `cchSrc` -1 değeri belirten dize gösterdiği olduğunu `lpSrcStr` null sonlandırılır. Bu durumda ve bu işlev, dize eşleştirme modunda kullanılan, işlevi dizenin uzunluğunu kendisini hesaplar ve içine depolanmış eşlenen dize null sonlandırır `*lpDestStr`.  
  
 `lpDestStr`  
 Uzun işaretçi arabellek için içine işlevi eşlenen dize veya sıralama anahtarı depolar.  
  
 `cchDest`  
 Karakter gösterdiği arabellek boyutu `lpDestStr`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa değerini `cchDest` sıfır olmayan, olan karakter veya bayt sayısı, `LCMAP_SORTKEY` belirtilen, yazılan arabellek başarılı olduğunu gösterir. Bu sayaç, bir NULL Sonlandırıcı yer içerir.  
  
 Varsa değerini `cchDest` sıfır, karakter veya bayt arabellek boyutu durumunda olduğundan `LCMAP_SORTKEY` çevrilmiş almak için gereken belirtilmişse, dize veya sıralama anahtarı başarı gösterir. Bu boyut NULL Sonlandırıcı yer içerir.  
  
 Sıfır başarısız olduğunu gösterir. Genişletilmiş hata bilgilerini için arama `GetLastError` işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `cchSrc` sıfırdan büyük ve `lpSrcStr` null ile sonlandırılmış bir dize `__crtLCMapStringW` ayarlar `cchSrc` dize uzunluğu. Ardından `__crtLCMapStringW` geniş dize (Unicode) sürümü çağırır `LCMapString` belirtilen parametrelerle işlevi. Bu işlevin dönüş değeri ve parametreleri hakkında daha fazla bilgi için bkz: `LCMapString` adresindeki işlev [MSDN Kitaplığı](http://go.microsoft.com/fwlink/p/?linkid=150542).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__crtLCMapStringW|awint.h|