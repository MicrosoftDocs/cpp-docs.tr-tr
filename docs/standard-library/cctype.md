---
title: '&lt;cctype&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cctype>
helpviewer_keywords:
- cctype header
ms.assetid: 3fd18bfd-c414-4def-bac1-c362e1fe8b71
ms.openlocfilehash: 19431d02e0742d63df058ca743fc0560131805bd
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244958"
---
# <a name="ltcctypegt"></a>&lt;cctype&gt;

Standart C Kitaplığı üstbilgisi içerir \<ctype.h > ve ilişkili adlar ekler `std` ad alanı.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<cctype >

**Namespace:** std

## <a name="remarks"></a>Açıklamalar

Bu üstbilginin dahil sağlar, standart C Kitaplığı üstbilgisinde harici bağlantı kullanılarak bildirilen adların bildirilir `std` ad alanı.

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

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
