---
description: 'Hakkında daha fazla bilgi edinin: &lt; stdexcept&gt;'
title: '&lt;stdexcept&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stdexcept>
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
ms.openlocfilehash: 07ab90442630c6dfb5a96604ba7c0cb6b214f605
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169092"
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;

Özel durum bildirmek için kullanılan birkaç standart sınıfı tanımlar. Sınıflar sınıf [özel](../standard-library/exception-class.md) durumundan türetilmiş bir türetme hiyerarşisi oluşturur ve iki genel özel durum türü içerir: mantıksal hatalar ve çalışma zamanı hataları. Mantıksal hatalar programcı hatalarına neden oldu. Logic_error temel sınıftan türetilir ve şunları içerir:

- `domain_error`

- `invalid_argument`

- `length_error`

- `out_of_range`

Çalışma zamanı hataları, kitaplık işlevlerinde veya çalışma zamanı sisteminde hatalar nedeniyle oluşur. Runtime_error temel sınıftan türetilir ve şunları içerir:

- `overflow_error`

- `range_error`

- `underflow_error`

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[domain_error sınıfı](../standard-library/domain-error-class.md)|Sınıfı, bir etki alanı hatasını raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[invalid_argument sınıfı](../standard-library/invalid-argument-class.md)|Sınıfı, geçersiz bir bağımsız değişkeni raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[length_error sınıfı](../standard-library/length-error-class.md)|Sınıfı, belirtilene çok uzun bir nesne oluşturma girişimini raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[logic_error sınıfı](../standard-library/logic-error-class.md)|Sınıfı, program yürütmeden önce, mantıksal önkoşulların ihlalleri gibi, hataları bildirmek üzere oluşan tüm özel durumlar için temel sınıf görevi görür.|
|[out_of_range sınıfı](../standard-library/out-of-range-class.md)|Sınıfı, geçerli aralığının dışında bir bağımsız değişkeni raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[overflow_error sınıfı](../standard-library/overflow-error-class.md)|Sınıfı, aritmetik taşma bildirmek üzere oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[range_error sınıfı](../standard-library/range-error-class.md)|Sınıfı, bir Aralık hatası bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|
|[runtime_error sınıfı](../standard-library/runtime-error-class.md)|Sınıfı, yalnızca program yürütüldüğünde oluşan hataları raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|
|[underflow_error sınıfı](../standard-library/underflow-error-class.md)|Sınıfı, aritmetik bir alt sınırın raporlanmak üzere oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
