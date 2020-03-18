---
title: bad_array_new_length sınıfı
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_array_new_length
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: c4f4f58f7b28960bbacf695a675fbe4f20a54192
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443709"
---
# <a name="bad_array_new_length-class"></a>bad_array_new_length sınıfı

Sınıf, sıfırdan küçük veya sınırından büyük bir ayırma isteğinin başarılı olmadığını göstermek için oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Açıklamalar

`what` tarafından döndürülen değer, uygulama tanımlı bir C dizesidir. Üye işlevlerinin hiçbiri özel durum oluşturmaz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** yeni \<>

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
