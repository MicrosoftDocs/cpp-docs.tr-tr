---
title: özel durum sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff6bc46fb8776de5f93b623b98f87513e710c603
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="exception-class"></a>exception Class

Sınıfı, belirli ifadeleri ve C++ Standart Kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.

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

Özellikle, bu taban sınıf içinde tanımlanan standart özel durum sınıfları köküdür [ \<stdexcept >](../standard-library/stdexcept.md). C dize tarafından döndürülen değeri `what` varsayılan oluşturucu tarafından belirtilmezse, ancak belirli türetilen sınıflar için oluşturucular tarafından uygulama tanımlı C dize olarak tanımlanabilir. Üye işlevleri hiçbiri tüm özel durumlar oluşturma.

`int` Parametresi bellek ayrılması gereken belirtmenize olanak verir. Değeri `int` göz ardı edilir.

> [!NOTE]
> Oluşturucular `exception(const char* const &message)` ve `exception(const char* const &message, int)` C++ Standart Kitaplığı için Microsoft uzantıları.

## <a name="example"></a>Örnek

Devralınan standart özel durum sınıfları kullanım örnekleri için `exception` sınıfı, tanımlanan sınıflarından herhangi biriyle bkz [ \<stdexcept >](../standard-library/stdexcept.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<özel durum >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
