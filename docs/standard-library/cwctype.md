---
title: '&lt;cwctype&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cwctype>
helpviewer_keywords:
- cwctype header
ms.assetid: 46476f95-b8c3-4ab2-a172-9a1be91124b7
ms.openlocfilehash: f6a754a96200e235cfc278746b1f0e5fc4ce018d
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243629"
---
# <a name="ltcwctypegt"></a>&lt;cwctype&gt;

Standart C Kitaplığı üstbilgisi içerir \<wctype.h > ve ilişkili adlar ekler `std` ad alanı.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cwctype>
```

## <a name="remarks"></a>Açıklamalar

Bu üstbilginin dahil sağlar, standart C Kitaplığı üstbilgisinde harici bağlantı kullanılarak bildirilen adların bildirilir `std` ad alanı.

## <a name="constants"></a>Sabitler

```cpp
namespace std {
    using wint_t = see below ;
    using wctrans_t = see below ;
    using wctype_t = see below ;
}

#define WEOF see below
```

## <a name="functions"></a>İşlevler

```cpp
int iswalnum(wint_t wc);
int iswalpha(wint_t wc);
int iswblank(wint_t wc);
int iswcntrl(wint_t wc);
int iswdigit(wint_t wc);
int iswgraph(wint_t wc);
int iswlower(wint_t wc);
int iswprint(wint_t wc);
int iswpunct(wint_t wc);
int iswspace(wint_t wc);
int iswupper(wint_t wc);
int iswxdigit(wint_t wc);
int iswctype(wint_t wc, wctype_t desc);
wctype_t wctype(const char* property);
wint_t towlower(wint_t wc);
wint_t towupper(wint_t wc);
wint_t towctrans(wint_t wc, wctrans_t desc);
wctrans_t wctrans(const char* property);
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
