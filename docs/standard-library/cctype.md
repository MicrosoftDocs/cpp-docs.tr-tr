---
title: '&lt;cctype&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cctype>
helpviewer_keywords:
- cctype header
ms.assetid: 3fd18bfd-c414-4def-bac1-c362e1fe8b71
ms.openlocfilehash: d1d69b5fe125372c489965949b2b59c4012fdec9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449842"
---
# <a name="ltcctypegt"></a>&lt;cctype&gt;

Standart C Kitaplığı üstbilgisi \<CType. h > içerir ve ilişkili adları `std` ad alanına ekler.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<cctype >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Bu üstbilginin dahil edilmesi, standart C Kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

## <a name="functions"></a>İşlevler

```cpp
int isalnum(int c);
int isalpha(int c);
int isblank(int c);
int iscntrl(int c);
int isdigit(int c);
int isgraph(int c);
int islower(int c);
int isprint(int c);
int ispunct(int c);
int isspace(int c);
int isupper(int c);
int isxdigit(int c);
int tolower(int c);
int toupper(int c);
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
