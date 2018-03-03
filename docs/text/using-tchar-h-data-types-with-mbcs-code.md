---
title: "TCHAR kullanma. _MBCS Kodu ile H veri türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tchar.h
- TCHAR
dev_langs:
- C++
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28255b2e47c48b89b0bd6aea044fe0c15c1f2a08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>_MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma
Zaman Bildirim sabiti **_MBCS** olan tanımlı, belirli bir genel metin yordamı yordamları şu tür birine eşler:  
  
-   Çok baytlı baytları, karakterleri ve dizeleri uygun şekilde işleyen bir SBCS yordamı. Bu durumda, dize bağımsız değişkeni tür olması beklenen **char\***. Örneğin, `_tprintf` eşlendiği `printf`; dize bağımsız değişkenleri `printf` türü **char\***. Kullanırsanız **_TCHAR** dizenizi genel metin veri türünü türleri, resmi ve gerçek parametre türleri için `printf` çünkü eşleşen **_TCHAR** \* eşlendiği **char \***.  
  
-   Bir MBCS özgü yordam. Bu durumda, dize bağımsız değişkeni tür olması beklenen `unsigned` **char\***. Örneğin, `_tcsrev` eşlendiği `_mbsrev`, bekler ve tür dizesi döndürür `unsigned` **char\***. Kullanırsanız **_TCHAR** , dize türleri için genel metin veri türü var. türü çakışma olasılığı nedeniyle **_TCHAR** yazmak için eşlenir `char`.  
  
 Bu tür çakışmayı (ve C derleyici uyarıları veya oluşturacağı C++ derleyici hataları) engellemek için üç çözümleri şunlardır:  
  
-   Varsayılan davranışını kullanın. Tchar.h yordamlar çalışma zamanı kitaplıkları, aşağıdaki örnekte olduğu gibi genel metin rutini prototipleri sağlar.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     Varsayılan durumda, prototipi `_tcsrev` eşlendiği `_mbsrev` aracılığıyla Libc.lib içinde bir dönüştürücü. Bu tür değiştirir `_mbsrev` gelen parametrelerini ve giden dönüş değerini **_TCHAR \***  (diğer bir deyişle, `char`  **\*** ) için `unsigned` `char` **\***. Bu yöntemi kullanırken eşleşen tür sağlar **_TCHAR**, ancak işlev çağırma yükünden nedeniyle nispeten daha yavaştır.  
  
-   İşlev satır içi kullanım kodunuzda aşağıdaki önişlemci deyimi kullanın.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Bu yöntem Tchar.h'de genel metin yordamını doğrudan uygun MBCS yordamına eşlemek için sağlanan bir satır içi işlev dönüştürücü neden olur. Aşağıdaki kod Alıntısı Tchar.h gelen bunun nasıl yapılacağı örneğidir.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     Kullanabileceğiniz ise satır içi kullanım, tür ve maliyet ek hiçbir zaman sahip garanti en iyi çözüm olmasıdır.  
  
-   Aşağıdaki önişlemci deyimi kodunuza doğrudan eşleme kullanın.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Varsayılan davranışı kullanmak istemiyorsanız veya kullanamaz, bu yaklaşım hızlı bir alternatif sağlayan satır içi kullanım. Makro tarafından doğrudan yordamının Tchar.h aşağıdaki örnekte olduğu gibi MBCS sürümüne eşlenmesi için genel metin yordamını neden olur.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     Bu yaklaşımı seçtiğinizde, dize bağımsız değişkenleri ve dize geri dönüş değerleri için uygun veri türleri kullanımını sağlamak dikkatli olmanız gerekir. Tür atama uygun türüyle eşleşen emin olmak için kullanabileceğiniz veya kullanabilirsiniz **_TXCHAR** genel metin veri türü. **_TXCHAR** yazmak için eşlenir `char` SBCS kod ancak yazmak için eşlenir `unsigned` `char` MBCS kodunda. Genel metin makroları hakkında daha fazla bilgi için bkz: [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tchar.h'de Genel Metin Eşlemeleri](../text/generic-text-mappings-in-tchar-h.md)