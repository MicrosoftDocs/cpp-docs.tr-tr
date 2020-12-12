---
description: 'Daha fazla bilgi edinin: C++ program başlatma ve sonlandırma'
title: C++ Program Başlatma ve Sonlandırma
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
ms.openlocfilehash: 644be6d4392f8e41b1d1cf7d45b484ed9903d463
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324793"
---
# <a name="c-program-startup-and-termination"></a>C++ Program Başlatma ve Sonlandırma

Bir C++ programı, program başlangıcında ve program sonlandırmada ve burada daha fazla özetlenen bir C programıyla aynı işlemleri gerçekleştirir.

Hedef ortam işlevi çağırmadan önce `main` ve statik süresine sahip tüm nesnelerde belirttiğiniz herhangi bir sabit değeri depoladıktan sonra program, bu tür statik nesneler için kalan oluşturucuları yürütür. Yürütme sırası, çeviri birimleri arasında belirtilmez, ancak bazı [Iostreams](../standard-library/iostreams-conventions.md) nesnelerinin bu statik oluşturucular tarafından kullanılmak üzere düzgün şekilde başlatıldığını varsayabilirsiniz. Bu denetim metni akışları şunlardır:

- Standart giriş için [cin](../standard-library/iostream.md#cin) .

- [cout](../standard-library/iostream.md#cout) — standart çıkış için.

- [cerr](../standard-library/iostream.md#cerr) — arabelleğe alınmamış standart hata çıktısı için.

- [CLOG](../standard-library/iostream.md#clog) — arabellekli standart hata çıktısı için.

Bu nesneleri, program sonlandırma sırasında statik nesneler için çağrılan Yıkıcılar içinde de kullanabilirsiniz.

C 'de olduğu gibi, `main` veya çağırma, `exit` `atexit` kayıt defterinin ters sırasıyla birlikte kaydedilen tüm işlevleri çağırır. Bu tür bir kayıtlı işlev çağrılarından oluşan özel durum `terminate` .

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
