---
title: TCHAR kullanma. _MBCS veri türleriyle H | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 066459593be4970fde141333a6f22f0846f8bbc4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412657"
---
# <a name="using-tcharh-data-types-with-mbcs"></a>MBCS ile TCHAR.H Veri Türlerini Kullanma

**Microsoft özel**

Genel metin rutin eşlemeler tabloda gösterildiği gibi (bkz [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)), ne zaman Bildirim sabiti **_MBCS** olan tanımlı, belirli bir genel metin yordamı şu tür birine eşler, yordamları:

- Çok baytlı baytları, karakterleri ve dizeleri uygun şekilde işleyen bir SBCS yordamı. Bu durumda, dize bağımsız değişkeni tür olması beklenen **char&#42;**. Örneğin, **_tprintf** eşlendiği **printf**; dize bağımsız değişkenleri **printf** türü **char&#42;**. Kullanırsanız **_TCHAR** dizenizi genel metin veri türünü türleri, resmi ve gerçek parametre türleri için **printf** çünkü eşleşen **_TCHAR&#42;**  eşler için **char&#42;**.

- Bir MBCS özgü yordam. Bu durumda, dize bağımsız değişkeni tür olması beklenen __imzasız char&#42;__. Örneğin, **_tcsrev** eşlendiği **_mbsrev**, bekler ve tür dizesi döndürür __imzasız char&#42;__. Yeniden kullanırsanız **_TCHAR** , dize türleri için genel metin veri türü var. türü çakışma olasılığı nedeniyle **_TCHAR** yazmak için eşlenir **char**.

 Bu tür çakışmayı (ve C derleyici uyarıları veya oluşturacağı C++ derleyici hataları) engellemek için üç çözümleri şunlardır:

- Varsayılan davranışını kullanın. TCHAR. H yordamlar çalışma zamanı kitaplıkları, aşağıdaki örnekte olduğu gibi genel metin rutini prototipleri sağlar.

   ```C
   char *_tcsrev(char *);
   ```

   Varsayılan durumda, prototipi **_tcsrev** eşlendiği **_mbsrev** aracılığıyla LIBC içinde bir dönüştürücü. LIB. Bu tür değiştirir **_mbsrev** gelen parametrelerini ve giden dönüş değerini **_TCHAR &#42;**  (gibi **char &#42;** ) için **İmzasız char &#42;**. Bu yöntemi kullanırken eşleşen tür sağlar **_TCHAR**, ancak bu işlev çağırma yükünden nedeniyle yavaştır.

- İşlev satır içi kullanım kodunuzda aşağıdaki önişlemci deyimi kullanın.

   ```C
   #define _USE_INLINING
   ```

   Bu yöntem TCHAR içinde sağlanan bir satır içi işlev dönüştürücü neden olur. H, genel metin yordamını doğrudan uygun MBCS yordamına eşlemek için kullanılır. Aşağıdaki kod Alıntısı TCHAR gelen. H bunun nasıl yapılacağı örneğidir.

   ```C
   __inline char *_tcsrev(char *_s1)
   {return (char *)_mbsrev((unsigned char *)_s1);}
   ```

   Kullanabileceğiniz ise satır içi kullanım, tür ve maliyet ek hiçbir zaman sahip garanti en iyi çözüm olmasıdır.

- Aşağıdaki önişlemci deyimi kodunuza "doğrudan eşleme" kullanın.

   ```C
   #define _MB_MAP_DIRECT
   ```

   Varsayılan davranışı kullanmak istemiyorsanız veya kullanamaz, bu yaklaşım hızlı bir alternatif sağlayan satır içi kullanım. Makro tarafından doğrudan yordamının TCHAR aşağıdaki örnekte olduğu gibi MBCS sürümüne eşlenmesi için genel metin yordamını neden olur. H.

   ```C
   #define _tcschr _mbschr
   ```

Bu yaklaşımı seçtiğinizde, uygun veri türleri dize bağımsız değişkenleri ve dize geri dönüş değerleri için kullanıldığından emin olmak için dikkatli olmanız gerekir. Tür atama uygun türüyle eşleşen emin olmak için kullanabileceğiniz veya kullanabilirsiniz **_TXCHAR** genel metin veri türü. **_TXCHAR** yazmak için eşlenir **char** SBCS kod ancak yazmak için eşlenir **imzasız char** MBCS kodunda. Genel metin makroları hakkında daha fazla bilgi için bkz: [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md).

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
