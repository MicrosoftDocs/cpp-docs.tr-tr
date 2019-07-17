---
title: bad_array_new_length sınıfı
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 823da1555119735e9aa1c46aa4db2e3a47affdec
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267963"
---
# <a name="badarraynewlength-class"></a>bad_array_new_length sınıfı

Sınıf bir ayırma isteği için dizi boyutu sıfırdan küçük veya bu değerden sınırına yapılamadı belirtmek için bir durum tanımlıyor.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what` bir uygulama tanımlı C dizesi. Üye işlevlerinin hiçbiri, tüm özel durumlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yeni >

## <a name="see-also"></a>Ayrıca bkz.

[exception Sınıfı](../standard-library/exception-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
