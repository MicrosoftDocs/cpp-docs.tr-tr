---
title: system_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::system_error
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
ms.openlocfilehash: 3f544cac1835a5a01e4d287cee1084bc56141716
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246234"
---
# <a name="systemerror-class"></a>system_error Sınıfı

Bir alt düzey sistem hatası rapor için oluşturulan tüm özel durumlar için temel sınıfı temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class system_error : public runtime_error {
    explicit system_error(error_code _Errcode, const string& _Message = "");
    system_error(error_code _Errcode, const char *_Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const string& _Message);
    system_error(error_code::value_type _Errval, const error_category& _Errcat, const char *_Message);
    
    const error_code& code() const throw();
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what` sınıfında [özel durum](../standard-library/exception-class.md) nesnesinden oluşturulan `_Message` ve türü depolanmış nesne [error_code](../standard-library/error-code-class.md) (ya da `code` veya `error_code(_Errval, _Errcat)`).

Üye işlevi `code` saklı döndürür [error_code](../standard-library/error-code-class.md) nesne.
