---
title: MBCS ile TCHAR.H Veri Türlerini Kullanma
ms.date: 11/04/2016
f1_keywords:
- _mbcs
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
ms.openlocfilehash: 487a73fae9380683e06e863f133e5e470635e0da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432688"
---
# <a name="using-tcharh-data-types-with-mbcs"></a>MBCS ile TCHAR.H Veri Türlerini Kullanma

**Microsoft'a özgü**

Genel metin yordam eşleşmeleri tablosunu belirtir (bkz [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)), Bildirim sabiti **_MBCS** olan tanımlanan, belirli bir genel metin yordam aşağıdaki tür birini eşler, yordamları:

- Çok baytlı bayt, karakterleri ve dizeleri uygun şekilde işler SBCS yordamı. Bu durumda, dize bağımsız değişkenleri türünde olması bekleniyor **char&#42;**. Örneğin, **_tprintf** eşlendiği **printf**; dize bağımsız değişkenleri **printf** türü **char&#42;**. Kullanırsanız **_TCHAR** genel metin veri türü, dize türleri, resmi ve gerçek parametre türleri için **printf** eşleşir çünkü **_TCHAR&#42;**  eşler için **char&#42;**.

- Bir MBCS özgü yordamı. Bu durumda, dize bağımsız değişkenleri türünde olması bekleniyor __imzasız char&#42;__. Örneğin, **_tcsrev** eşlendiği **_mbsrev**, bekliyor ve bir dize türü döndürür __imzasız char&#42;__. Yeniden kullanırsanız **_TCHAR** , dize türleri için genel metin veri türü var. türü çakışma olasılığı nedeniyle **_TCHAR** türüne haritalar **char**.

Bu tür çakışması (ve C Derleyici uyarılarını veya neden olan C++ derleyici hataları) engel için üç çözümler aşağıda verilmiştir:

- Varsayılan davranışı kullanın. TCHAR. H genel metin yordam prototipleri aşağıdaki örnekte olduğu gibi çalışma zamanı kitaplığı yordamları sağlar.

   ```C
   char *_tcsrev(char *);
   ```

   Varsayılan durumda, prototipi **_tcsrev** eşlendiği **_mbsrev** aracılığıyla LIBC içinde bir dönüştürücü. LIB. Bu tür değişiklikleri **_mbsrev** gelen parametreleri ve giden dönüş değerini **_TCHAR &#42;**  (gibi **char &#42;** ) için **İmzasız char &#42;**. Bu yöntem kullanırken eşleşen türü sağlar **_TCHAR**, ancak işlev çağrısı yükü nedeniyle görece yavaş olacaktır.

- Aşağıdaki önişlemci deyim, kodunuzda satır içi işlevi kullanın.

   ```C
   #define _USE_INLINING
   ```

   Bu yöntem TCHAR sağlanan bir satır içi işlev dönüştürücü neden olur. H, genel metin yordam doğrudan uygun MBCS yordamına eşlemek için kullanılır. TCHAR alınan aşağıdaki kod alıntıda. H bunun nasıl yapıldığına bir örnek sağlar.

   ```C
   __inline char *_tcsrev(char *_s1)
   {return (char *)_mbsrev((unsigned char *)_s1);}
   ```

   Kullanabileceğiniz, satır içi kullanım, tür ve hiçbir ek süre olan maliyet garanti eder, en iyi çözümü olmasıdır.

- Kodunuzda aşağıdaki önişlemci ifadesi "doğrudan eşleme" kullanın.

   ```C
   #define _MB_MAP_DIRECT
   ```

   Varsayılan davranışı kullanmak istemiyorsanız veya kullanamazsınız, bu yaklaşım hızlı bir alternatif sağlar. satır içi kullanım. Genel metin yordam TCHAR aşağıdaki örnekte olduğu gibi yordamı MBCS sürümü için doğrudan bir makro tarafından eşleştirilecek neden olur. H

   ```C
   #define _tcschr _mbschr
   ```

Bu yaklaşımı benimsemeniz, uygun veri türü dize bağımsız değişkenleri ve dönüş değerleri dize için kullanıldığından emin olmak için dikkatli olmanız gerekir. Tür atama uygun tür eşleşmesini sağlamak için kullanabileceğiniz veya kullanabileceğiniz **_TXCHAR** genel metin veri türü. **_TXCHAR** türüne haritalar **char** SBCS kod ancak türüne haritalar **imzasız char** MBCS kod. Genel metin makrolar hakkında daha fazla bilgi için bkz. [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
