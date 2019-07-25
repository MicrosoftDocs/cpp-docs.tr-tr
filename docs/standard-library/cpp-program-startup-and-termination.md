---
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
ms.openlocfilehash: e59e8852172a998e4bf4f42f9f919dc29c2ded85
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450646"
---
# <a name="c-program-startup-and-termination"></a>C++ Program Başlatma ve Sonlandırma

C++ Program, program başlangıcında ve program sonlandırmada ve burada daha fazla özetlenen şekilde bir C programıyla aynı işlemleri gerçekleştirir.

Hedef ortam işlevi `main`çağırmadan önce ve statik süresine sahip tüm nesnelerde belirttiğiniz herhangi bir sabit değeri depoladıktan sonra program, bu tür statik nesneler için kalan oluşturucuları yürütür. Yürütme sırası, çeviri birimleri arasında belirtilmez, ancak bazı [Iostreams](../standard-library/iostreams-conventions.md) nesnelerinin bu statik oluşturucular tarafından kullanılmak üzere düzgün şekilde başlatıldığını varsayabilirsiniz. Bu denetim metni akışları şunlardır:

- Standart giriş için [cin](../standard-library/iostream.md#cin) .

- [cout](../standard-library/iostream.md#cout) — standart çıkış için.

- [cerr](../standard-library/iostream.md#cerr) — arabelleğe alınmamış standart hata çıktısı için.

- [CLOG](../standard-library/iostream.md#clog) — arabellekli standart hata çıktısı için.

Bu nesneleri, program sonlandırma sırasında statik nesneler için çağrılan Yıkıcılar içinde de kullanabilirsiniz.

C 'de olduğu gibi, `main` veya çağırma `exit` , kayıt defterinin ters sırasıyla birlikte `atexit` kaydedilen tüm işlevleri çağırır. Bu tür bir kayıtlı işlev çağrılarından `terminate`oluşan özel durum.

## <a name="see-also"></a>Ayrıca bkz.

[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
