---
title: "TCHAR kullanma. _MBCS veri türleriyle H | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c015c8ff7481f0d5ba25eba023b21f4877deaa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-tcharh-data-types-with-mbcs"></a>MBCS ile TCHAR.H Veri Türlerini Kullanma
**Microsoft özel**  
  
 Genel metin rutin eşlemeler tabloda gösterildiği gibi (bkz [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)), ne zaman Bildirim sabiti `_MBCS` olan tanımlı, belirli bir genel metin yordamı yordamları şu tür birine eşler:  
  
-   Çok baytlı baytları, karakterleri ve dizeleri uygun şekilde işleyen bir SBCS yordamı. Bu durumda, dize bağımsız değişkeni tür olması beklenen `char*`. Örneğin, `_tprintf` eşlendiği `printf`; dize bağımsız değişkenleri `printf` türü `char*`. Kullanırsanız `_TCHAR` dizenizi genel metin veri türünü türleri, resmi ve gerçek parametre türleri için `printf` çünkü eşleşen `_TCHAR*` eşlendiği `char*`.  
  
-   Bir MBCS özgü yordam. Bu durumda, dize bağımsız değişkeni tür olması beklenen `unsigned char*`. Örneğin, `_tcsrev` eşlendiği `_mbsrev`, bekler ve tür dizesi döndürür `unsigned char*`. Yeniden kullanırsanız `_TCHAR` , dize türleri için genel metin veri türü var. türü çakışma olasılığı nedeniyle `_TCHAR` yazmak için eşlenir `char`.  
  
 Bu tür çakışmayı (ve C derleyici uyarıları veya oluşturacağı C++ derleyici hataları) engellemek için üç çözümleri şunlardır:  
  
-   Varsayılan davranışını kullanın. TCHAR. H yordamlar çalışma zamanı kitaplıkları, aşağıdaki örnekte olduğu gibi genel metin rutini prototipleri sağlar.  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     Varsayılan durumda, prototipi `_tcsrev` eşlendiği `_mbsrev` aracılığıyla LIBC içinde bir dönüştürücü. LIB. Bu tür değiştirir `_mbsrev` gelen parametrelerini ve giden dönüş değerini `_TCHAR *` (gibi `char *`) için `unsigned char *`. Bu yöntemi kullanırken eşleşen tür sağlar `_TCHAR`, ancak bu işlev çağırma yükünden nedeniyle yavaştır.  
  
-   İşlev satır içi kullanım kodunuzda aşağıdaki önişlemci deyimi kullanın.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Bu yöntem TCHAR içinde sağlanan bir satır içi işlev dönüştürücü neden olur. H, genel metin yordamını doğrudan uygun MBCS yordamına eşlemek için kullanılır. Aşağıdaki kod Alıntısı TCHAR gelen. H bunun nasıl yapılacağı örneğidir.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     Kullanabileceğiniz ise satır içi kullanım, tür ve maliyet ek hiçbir zaman sahip garanti en iyi çözüm olmasıdır.  
  
-   Aşağıdaki önişlemci deyimi kodunuza "doğrudan eşleme" kullanın.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Varsayılan davranışı kullanmak istemiyorsanız veya kullanamaz, bu yaklaşım hızlı bir alternatif sağlayan satır içi kullanım. Makro tarafından doğrudan yordamının TCHAR aşağıdaki örnekte olduğu gibi MBCS sürümüne eşlenmesi için genel metin yordamını neden olur. H.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 Bu yaklaşımı seçtiğinizde, uygun veri türleri dize bağımsız değişkenleri ve dize geri dönüş değerleri için kullanıldığından emin olmak için dikkatli olmanız gerekir. Tür atama uygun türüyle eşleşen emin olmak için kullanabileceğiniz veya kullanabilirsiniz `_TXCHAR` genel metin veri türü. `_TXCHAR`yazmak için eşlenir `char` SBCS kod ancak yazmak için eşlenir `unsigned char` MBCS kodunda. Genel metin makroları hakkında daha fazla bilgi için bkz: [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uluslararası duruma getirme](../c-runtime-library/internationalization.md)   
 [Kategorilere göre çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)