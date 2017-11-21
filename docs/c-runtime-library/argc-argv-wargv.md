---
title: __argc, __argv, __wargv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wargv
- __argv
- __argc
apilocation: msvcrt120.dll
apitype: DLLExport
f1_keywords:
- __argv
- __argc
- __wargv
dev_langs: C++
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbb6e0886844cda7142ee52fcb545e122c38ea8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="argc-argv-wargv"></a>__argc, __argv, __wargv
`__argc` Genel değişkeni, programa geçirilen komut satırı bağımsız değişkenleri sayısını. `__argv`bir program değişkenleri içeren tek bayt karakter ya da çok byte karakterlik bir dize dizisi işaretçidir ve `__wargv` gösteren bir işaretçidir program değişkenleri içeren bir joker karakter dizeler dizisi. Bu genel değişkenler bağımsız değişkenleri sağlayın `main` veya `wmain`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extern int __argc;  
extern char ** __argv;  
extern wchar_t ** __wargv;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanan bir programda `main` işlevi, `__argc` ve `__argv` program başlangıcında programı başlatmak için kullanılan komut satırını kullanarak başlatılır. Komut satırı bağımsız değişkenleri ayrıştırılır ve joker karakterler genişletilir. Bağımsız değişken sayısı atandığı `__argc` bağımsız değişkeni dizeleri yığında ayrılan ve bağımsız değişkenler dizisi için bir işaretçi atandığı `__argv`. Geniş karakterler kullanmak için derlenmiş bir programda ve `wmain` işlevi, bağımsız değişkenler Ayrıştırılan ve joker karakterleri joker karakter dizeleri olarak genişletilmiş ve bağımsız değişken bir dize dizisi için bir işaretçi atandığı `__wargv`.  
  
 Taşınabilir kodunu için geçirilen bağımsız değişkenler kullandığınız olan öneririz `main` programın komut satırı bağımsız değişkenleri alınamıyor.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE tanımlı değil|_UNICODE tanımlanmış|  
|---------------------|---------------------------|-----------------------|  
|`__targv`|`__argv`|`__wargv`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Genel değişkeni|Gerekli başlık|  
|---------------------|---------------------|  
|`__argc`, `__argv`, `__wargv`|\<stdlib.h >, \<cstdlib > (C++)|  
  
 `__argc`, `__argv`, ve `__wargv` Microsoft uzantıları. Uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel değişkenler](../c-runtime-library/global-variables.md)   
 [Main: Program başlatma](../cpp/main-program-startup.md)   
 [Main yerine wmain kullanma](../cpp/using-wmain-instead-of-main.md)