---
title: MBCS ile TCHAR.H Veri Türlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
ms.openlocfilehash: d1aab0c21a348e4b1a6e85a7adb7f7f8ea1587b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87188641"
---
# <a name="using-tcharh-data-types-with-_mbcs"></a>MBCS ile TCHAR.H Veri Türlerini Kullanma

**Microsoft'a Özgü**

Genel metin rutin eşlemelerinin tablosu (bkz. [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)), bildirim sabiti **_MBCS** tanımlandığında, belirli bir genel metin yordamı aşağıdaki yordam türlerinden biriyle eşlenir:

- Çok baytlı baytları, karakterleri ve dizeleri uygun şekilde işleyen bir SBCS yordamı. Bu durumda, dize bağımsız değişkenlerinin **char&#42;** türünde olması beklenir. Örneğin, **_tprintf** **printf**ile eşlenir; **printf** dize bağımsız değişkenleri **char&#42;** türündedir. Dize türleriniz için **_TCHAR** genel metin veri türünü kullanırsanız, **_TCHAR&#42;** **char&#42;** ile eşlendiği için **printf** eşleşmesi için biçimsel ve gerçek parametre türleri.

- MBCS 'ye özgü bir yordamdır. Bu durumda, dize bağımsız değişkenlerinin __işaretsiz char&#42;__ türünde olması beklenir. Örneğin, **_tcsrev** **_mbsrev**eşlenir ve __işaretsiz char&#42;__ türünde bir dize bekler ve döndürür. Yine, dize türleriniz için **_TCHAR** genel metin veri türünü kullanırsanız, **_TCHAR** tür olarak eşlendiği için olası bir tür çakışması vardır **`char`** .

Aşağıda, bu tür çakışmasını önlemek için üç çözüm bulunur (ve sonuç olarak C derleyicisi uyarıları veya C++ derleyici hataları):

- Varsayılan davranışı kullanın. 'Ta. H, aşağıdaki örnekte olduğu gibi çalışma zamanı kitaplıklarında yordamlar için genel metin rutin prototürler sağlar.

   ```C
   char *_tcsrev(char *);
   ```

   Varsayılan durumda, **_tcsrev** için prototip, libc 'teki bir dönüştürücü aracılığıyla **_mbsrev** eşlenir. LIB. Bu, **_mbsrev** gelen parametrelerin türlerini ve giden dönüş değerini **_TCHAR &#42;** ( **char &#42;** gibi) **işaretsiz char &#42;** olarak değiştirir. Bu yöntem **_TCHAR**kullanırken tür eşleştirmeyi sağlar, ancak işlev çağrı yükü nedeniyle oldukça yavaştır.

- Kodunuzda aşağıdaki Önişlemci ifadesini ekleyerek işlevi satır içinde kullanın.

   ```C
   #define _USE_INLINING
   ```

   Bu yöntem, TCHAR içinde sunulan bir satır içi işlev Dönüştürücüsü oluşturulmasına neden olur. H, genel metin yordamını doğrudan uygun MBCS yordamıyla eşlemek için. Aşağıdaki kod TCHAR 'dan alıntı yapılır. H bunun nasıl yapıldığını gösteren bir örnek sağlar.

   ```C
   __inline char *_tcsrev(char *_s1)
   {return (char *)_mbsrev((unsigned char *)_s1);}
   ```

   Satır içi ' ı kullanacaksanız, bu en iyi çözümdür çünkü tür eşleşmesini garanti eder ve ek bir zaman maliyeti yoktur.

- Aşağıdaki önişlemci bildirisini kodunuza ekleyerek "doğrudan eşleme" kullanın.

   ```C
   #define _MB_MAP_DIRECT
   ```

   Bu yaklaşım, varsayılan davranışı kullanmak istemiyorsanız veya satır içi kullanmıyorsanız hızlı bir alternatif sağlar. Aşağıdaki örnekte gösterildiği gibi, genel metin yordamının bir makro tarafından doğrudan, yordamın MBCS sürümüne eşlenmesine neden olur. Olsun.

   ```C
   #define _tcschr _mbschr
   ```

Bu yaklaşımı uyguladığınızda, dize bağımsız değişkenleri ve dize dönüş değerleri için uygun veri türlerinin kullanıldığından emin olmak için dikkatli olmanız gerekir. Uygun tür eşleşmesini sağlamak için tür atama kullanabilirsiniz veya **_TXCHAR** genel metin veri türünü kullanabilirsiniz. **_TXCHAR** **`char`** , SBCS kodunda türüyle EŞLENIR, ancak MBCS kodunda tür ile eşlenir **`unsigned char`** . Genel metin makroları hakkında daha fazla bilgi için bkz. [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
