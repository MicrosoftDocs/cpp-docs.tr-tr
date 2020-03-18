---
title: _MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
ms.openlocfilehash: 78e5d89e1e87d081e762fab1298eb990b914324c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446596"
---
# <a name="using-tcharh-data-types-with-_mbcs-code"></a>_MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma

`_MBCS` bildirim sabiti tanımlandığında, belirli bir genel metin yordamı aşağıdaki yordam türlerinden biriyle eşlenir:

- Çok baytlı baytları, karakterleri ve dizeleri uygun şekilde işleyen bir SBCS yordamı. Bu durumda, dize bağımsız değişkenlerinin `char*`türünde olması beklenir. Örneğin, `_tprintf` `printf`eşlenir; `printf` dize bağımsız değişkenleri `char*`türündedir. Dize türleriniz için `_TCHAR` genel metin veri türünü kullanırsanız, `_TCHAR*` `char*`eşlendiği için biçimsel ve gerçek parametre türleri `printf` eşleşir.

- MBCS 'ye özgü bir yordamdır. Bu durumda, dize bağımsız değişkenlerinin `unsigned char*`türünde olması beklenir. Örneğin, `_tcsrev`, `unsigned char*`türünde bir dize bekleyen ve döndüren `_mbsrev`eşlenir. Dize türleriniz için `_TCHAR` genel metin veri türünü kullanırsanız, `_TCHAR` tür `char`eşlendiği için olası bir tür çakışması vardır.

Aşağıda, bu tür çakışmasını önlemek için üç çözüm bulunur (ve sonuç olarak C derleyicisi C++ uyarıları veya derleyici hataları):

- Varsayılan davranışı kullanın. Tchar. h, aşağıdaki örnekte olduğu gibi çalışma zamanı kitaplıklarında yordamlar için genel metin rutin prototipleri sağlar.

    ```cpp
    char * _tcsrev(char *);
    ```

   Varsayılan durumda, `_tcsrev` için prototip, libc. lib içindeki bir dönüştürücü aracılığıyla `_mbsrev` eşlenir. Bu, `_mbsrev` gelen parametrelerin türlerini ve giden dönüş değerini `_TCHAR*` (yani `char *`) `unsigned char *`olarak değiştirir. Bu yöntem `_TCHAR`kullanırken tür eşleştirmeyi sağlar, ancak işlev çağrısı yükü nedeniyle oldukça yavaştır.

- Kodunuzda aşağıdaki Önişlemci ifadesini ekleyerek işlevi satır içinde kullanın.

    ```cpp
    #define _USE_INLINING
    ```

   Bu yöntem, genel metin yordamını doğrudan uygun MBCS yordamına eşlemek için Tchar. h içinde sunulan bir satır içi işlev dönüştürücü sağlar. Tchar. h 'dan alınan aşağıdaki kod, bunun nasıl yapıldığını gösteren bir örnek sağlar.

    ```cpp
    __inline char *_tcsrev(char *_s1)
    {return (char *)_mbsrev((unsigned char *)_s1);}
    ```

   Satır içi ' ı kullanacaksanız, bu en iyi çözümdür çünkü tür eşleşmesini garanti eder ve ek bir zaman maliyeti yoktur.

- Kodunuzda aşağıdaki Önişlemci ifadesini ekleyerek doğrudan eşlemeyi kullanın.

    ```cpp
    #define _MB_MAP_DIRECT
    ```

   Bu yaklaşım, varsayılan davranışı kullanmak istemiyorsanız veya satır içi kullanmıyorsanız hızlı bir alternatif sağlar. Bu, genel metin yordamının bir makro tarafından doğrudan yordamın MBCS sürümüne eşlenmesine neden olur, bu da Tchar. h 'den aşağıdaki örnekte olduğu gibi.

    ```cpp
    #define _tcschr _mbschr
    ```

   Bu yaklaşımı uyguladığınızda, dize bağımsız değişkenleri ve dize dönüş değerleri için uygun veri türlerinin kullanılmasına dikkat etmeniz gerekir. Uygun tür eşleşmesini sağlamak için tür atama kullanabilirsiniz veya `_TXCHAR` genel metin veri türünü kullanabilirsiniz. `_TXCHAR`, SBCS kodundaki **char** türüne eşlenir, ancak MBCS kodunda **işaretsiz char** türüyle eşlenir. Genel metin makroları hakkında daha fazla bilgi için bkz. *çalışma zamanı kitaplık başvurusunda* [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Tchar.h'de Genel Metin Eşlemeleri](../text/generic-text-mappings-in-tchar-h.md)
