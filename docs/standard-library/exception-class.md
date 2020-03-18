---
title: exception Class
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: 5bef8190889ae00298760ea395fb524f557c2be2
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446822"
---
# <a name="exception-class"></a>exception Class

Sınıfı, belirli ifadeler ve C++ standart kitaplık tarafından oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Sözdizimi

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
};
```

## <a name="remarks"></a>Açıklamalar

Özellikle, bu temel sınıf, [\<stdexcept >](../standard-library/stdexcept.md)tanımlanan standart özel durum sınıflarının köküdür. `what` tarafından döndürülen C dizesi değeri varsayılan Oluşturucu tarafından belirtilmemiş, ancak uygulama tanımlı bir C dizesi olarak belirli türetilmiş sınıfların oluşturucuları tarafından tanımlanabilir. Üye işlevlerinin hiçbiri özel durum oluşturmaz.

**İnt** parametresi, hiçbir belleğin ayrılmamalıdır belirtmenize izin verir. **İnt** değeri yok sayılır.

> [!NOTE]
> `exception(const char* const &message)` ve `exception(const char* const &message, int)` oluşturucular, C++ standart kitaplık için Microsoft uzantılarıdır.

## <a name="example"></a>Örnek

`exception` sınıfından devraldığı standart özel durum sınıflarının kullanımıyla ilgili örnekler için, bkz. [\<stdexcept >](../standard-library/stdexcept.md)tanımlanmış sınıflar.
