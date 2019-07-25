---
title: bad_array_new_length sınıfı
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: b00042513364ac04b62ac7e1943d912dcb78f212
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459496"
---
# <a name="badarraynewlength-class"></a>bad_array_new_length sınıfı

Sınıf, sıfırdan küçük veya sınırından büyük bir ayırma isteğinin başarılı olmadığını göstermek için oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Açıklamalar

Tarafından `what` döndürülen değer, uygulama tanımlı bir C dizesidir. Üye işlevlerinin hiçbiri özel durum oluşturmaz.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yeni >

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
