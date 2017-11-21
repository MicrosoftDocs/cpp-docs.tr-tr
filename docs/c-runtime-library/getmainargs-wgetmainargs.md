---
title: __getmainargs, __wgetmainargs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wgetmainargs
- __getmainargs
apilocation:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __wgetmainargs
- __getmainargs
dev_langs: C++
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bd386aba0f5693538d9aae61bcf7c2384b6052bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="getmainargs-wgetmainargs"></a>__getmainargs, __wgetmainargs
Komut satırı ayrıştırma çağırır ve bağımsız değişkenleri kopyalar `main()` geçirilen işaretçileri geriye doğru.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Argc`  
 Takip edin bağımsız değişken sayısı içeren bir tamsayı `argv`. `argc` parametresi her zaman 1'e eşit veya daha büyüktür.  
  
 `_Argv`  
 Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural tarafından `argv[0]` ile program çağrılan komut, argv [1] ilk komut satırı bağımsız değişkeni ve vb. [argc] argv kadar her zaman NULL. Her zaman ilk komut satırı bağımsız değişkeni olan `argv[1]` ve son `argv[argc - 1]`.  
  
 `_Env`  
 Kullanıcının ortama değişkenlerini temsil eden bir dizeler dizisi. Bu dizi NULL giriş tarafından sonlandırıldı.  
  
 `_DoWildCard`  
 Tamsayı, komut satırı bağımsız değişkenleri joker karakter 1 olarak ayarlanırsa genişletir veya 0 olarak ayarlanırsa hiçbir şey yapmaz.  
  
 `_StartInfo`  
 CRT DLL geçirilecek diğer bilgileri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 başarılı olursa 0; negatif bir değer başarısız olursa.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `__getmainargs` wide olmayan karakter platformlarda ve `__wgetmainargs` joker karakter (Unicode) platformlarda.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|__getmainargs|internal.h|  
|__wgetmainargs|internal.h|