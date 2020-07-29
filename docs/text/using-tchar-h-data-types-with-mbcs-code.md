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
ms.openlocfilehash: dd43c29d77c3351e8f597b474c4756ad3d45ef2b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215367"
---
# <a name="using-tcharh-data-types-with-_mbcs-code"></a>_MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma

Bildirim sabiti `_MBCS` tanımlandığında, belirli bir genel metin yordamı aşağıdaki yordam türlerinden biriyle eşlenir:

- Çok baytlı baytları, karakterleri ve dizeleri uygun şekilde işleyen bir SBCS yordamı. Bu durumda, dize bağımsız değişkenlerinin türünde olması beklenir **`char*`** . Örneğin, `_tprintf` ile eşlenir `printf` ; dize bağımsız değişkenleri `printf` tür **`char*`** . `_TCHAR`Dize türleriniz için genel metin veri türünü kullanırsanız, ile eşleşen biçimsel ve gerçek parametre türleri ile `printf` `_TCHAR*` eşlenir **`char*`** .

- MBCS 'ye özgü bir yordamdır. Bu durumda, dize bağımsız değişkenlerinin türünde olması beklenir `unsigned char*` . Örneğin, `_tcsrev` öğesine eşlenir `_mbsrev` ve türünde bir dize bekler ve döndürür `unsigned char*` . `_TCHAR`Dize türleriniz için genel metin veri türünü kullanırsanız, eşlenecek bir tür çakışması var `_TCHAR` **`char`** .

Aşağıda, bu tür çakışmasını önlemek için üç çözüm bulunur (ve sonuç olarak C derleyicisi uyarıları veya C++ derleyici hataları):

- Varsayılan davranışı kullanın. Tchar. h, aşağıdaki örnekte olduğu gibi çalışma zamanı kitaplıklarında yordamlar için genel metin rutin prototipleri sağlar.

    ```cpp
    char * _tcsrev(char *);
    ```

   Varsayılan durumda, için prototipi `_tcsrev` `_mbsrev` libc. lib içindeki bir dönüştürücü aracılığıyla ile eşlenir. Bu, `_mbsrev` gelen parametrelerin türlerini ve giden dönüş değerini `_TCHAR*` (yani, `char *` ) olarak değiştirir `unsigned char *` . Bu yöntem, kullanırken tür eşleşmesini sağlar `_TCHAR` , ancak işlev çağrısı yükü nedeniyle nispeten yavaştır.

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

   Bu yaklaşımı uyguladığınızda, dize bağımsız değişkenleri ve dize dönüş değerleri için uygun veri türlerinin kullanılmasına dikkat etmeniz gerekir. Uygun tür eşleşmesini sağlamak için tür atama kullanabilirsiniz veya `_TXCHAR` Genel metin veri türünü kullanabilirsiniz. `_TXCHAR`SBCS kodunda türüyle eşlenir, **`char`** ancak MBCS kodunda tür ile eşlenir **`unsigned char`** . Genel metin makroları hakkında daha fazla bilgi için bkz. *çalışma zamanı kitaplık başvurusunda* [Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Tchar. h 'de Genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md)
