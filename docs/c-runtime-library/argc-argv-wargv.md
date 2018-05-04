---
title: __argc, __argv, __wargv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __wargv
- __argv
- __argc
apilocation:
- msvcrt120.dll
apitype: DLLExport
f1_keywords:
- __argv
- __argc
- __wargv
dev_langs:
- C++
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d5d9762f02a06e697ce164910755431e8a59009
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="argc-argv-wargv"></a>__argc, __argv, __wargv
`__argc` Genel değişkeni, programa geçirilen komut satırı bağımsız değişkenleri sayısını. `__argv` bir program değişkenleri içeren tek bayt karakter ya da çok byte karakterlik bir dize dizisi işaretçidir ve `__wargv` gösteren bir işaretçidir program değişkenleri içeren bir joker karakter dizeler dizisi. Bu genel değişkenler bağımsız değişkenleri sağlayın `main` veya `wmain`.  
  
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
 [main Yerine wmain Kullanma](../cpp/using-wmain-instead-of-main.md)