---
title: _MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma
ms.date: 11/04/2016
f1_keywords:
- tchar.h
- TCHAR
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
ms.openlocfilehash: 62801cfc2386cf2aee7fd35a5e589d73b4f91918
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742018"
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>_MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma

Olduğunda bildirim sabiti `_MBCS` olan tanımlanan, belirli bir genel metin yordam yordamlar aşağıdaki türde birini eşler:

- Çok baytlı bayt, karakterleri ve dizeleri uygun şekilde işler SBCS yordamı. Bu durumda, dize bağımsız değişkenleri türünde olması bekleniyor `char*`. Örneğin, `_tprintf` eşlendiği `printf`; dize bağımsız değişkenleri `printf` türü `char*`. Kullanırsanız `_TCHAR` genel metin veri türü, dize türleri, resmi ve gerçek parametre türleri için `printf` eşleşir çünkü `_TCHAR*` eşlendiği `char*`.

- Bir MBCS özgü yordamı. Bu durumda, dize bağımsız değişkenleri türünde olması bekleniyor `unsigned char*`. Örneğin, `_tcsrev` eşlendiği `_mbsrev`, bekliyor ve bir dize türü döndürür `unsigned char*`. Kullanırsanız `_TCHAR` , dize türleri için genel metin veri türü var. türü çakışma olasılığı nedeniyle `_TCHAR` türüne haritalar `char`.

Bu tür çakışması (ve C Derleyici uyarılarını veya neden olan C++ derleyici hataları) engel için üç çözümler aşağıda verilmiştir:

- Varsayılan davranışı kullanın. Tchar.h genel metin yordam prototipleri aşağıdaki örnekte olduğu gibi çalışma zamanı kitaplığı yordamları sağlar.

    ```cpp
    char * _tcsrev(char *);
    ```

   Varsayılan durumda, prototipi `_tcsrev` eşlendiği `_mbsrev` aracılığıyla /ML içinde bir dönüştürücü. Bu tür değişiklikleri `_mbsrev` gelen parametreleri ve giden dönüş değerini `_TCHAR*` (diğer bir deyişle, `char *`) için `unsigned char *`. Bu yöntem kullanırken eşleşen türü sağlar `_TCHAR`, ancak işlev çağrısı yükü nedeniyle nispeten daha yavaştır.

- Aşağıdaki önişlemci deyim, kodunuzda satır içi işlevi kullanın.

    ```cpp
    #define _USE_INLINING
    ```

   Bu yöntem, sağlanan Tchar.h'de genel metin yordam doğrudan uygun MBCS yordamına eşlemek için bir satır içi işlev dönüştürücü neden olur. Tchar.h alınan aşağıdaki kod alıntıda bunun nasıl yapıldığına bir örnek sağlar.

    ```cpp
    __inline char *_tcsrev(char *_s1)
    {return (char *)_mbsrev((unsigned char *)_s1);}
    ```

   Kullanabileceğiniz, satır içi kullanım, tür ve hiçbir ek süre olan maliyet garanti eder, en iyi çözümü olmasıdır.

- Aşağıdaki önişlemci deyim, kodunuzda doğrudan eşleme kullanın.

    ```cpp
    #define _MB_MAP_DIRECT
    ```

   Varsayılan davranışı kullanmak istemiyorsanız veya kullanamazsınız, bu yaklaşım hızlı bir alternatif sağlar. satır içi kullanım. Tchar.h aşağıdaki örnekte olduğu gibi yordamı MBCS sürümü için doğrudan bir makro tarafından eşleştirilecek genel metin yordam neden olur.

    ```cpp
    #define _tcschr _mbschr
    ```

   Bu yaklaşımı benimsemeniz, dize bağımsız değişkenleri ve dönüş değerleri dize için uygun veri türlerinin kullanımı emin olmak dikkatli olmanız gerekir. Tür atama uygun tür eşleşmesini sağlamak için kullanabileceğiniz veya kullanabileceğiniz `_TXCHAR` genel metin veri türü. `_TXCHAR` yazmak için maps **char** SBCS kod ancak türüne haritalar **imzasız char** MBCS kod. Genel metin makrolar hakkında daha fazla bilgi için bkz. [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md) içinde *çalışma zamanı kitaplığı başvurusu*.

## <a name="see-also"></a>Ayrıca bkz.

[Tchar.h'de Genel Metin Eşlemeleri](../text/generic-text-mappings-in-tchar-h.md)
