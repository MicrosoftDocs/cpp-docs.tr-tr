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
ms.openlocfilehash: 2246e50c81da9eb505fd30cfa31f9f24e3fe4703
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210768"
---
# <a name="c-program-startup-and-termination"></a>C++ Program Başlatma ve Sonlandırma

Program başlatma ve sonlandırma program yanı sıra, daha da aşağıda ana hatlarıyla belirtilen birkaç C programı gibi bir C++ programını aynı işlemleri gerçekleştirir.

Önce hedef ortam işlevi çağırır. `main`, ve statik süresi olan tüm nesneleri belirttiğiniz tüm sabit başlangıç değerlerini depolar sonra kalan hiçbir oluşturucu gibi statik nesneler için program yürütür. Yürütme sırası çeviri birimleri arasında belirtilmedi, ancak yine de bazı kabul edebilirsiniz [iostreams](../standard-library/iostreams-conventions.md) nesneleri bu statik oluşturucular tarafından kullanılmak üzere doğru şekilde başlatılır. Bu denetim metin akışları şunlardır:

- [cin](../standard-library/iostream.md#cin) — standart giriş.

- [cout](../standard-library/iostream.md#cout) — standart çıktı.

- [cerr](../standard-library/iostream.md#cerr) — çıkarılan standart hata çıktısı için.

- [clog](../standard-library/iostream.md#clog) — için arabelleğe alınan standart hata çıktısı.

Program sonlandırma sırasında statik nesneler için adlandırılan yok ediciler içinde bu nesneler de kullanabilirsiniz.

Visual c gibi döndürme `main` veya çağırma `exit` kayıtlı tüm işlevleri çağırır `atexit` ters sırada kayıt defterinin. Böyle bir durum kayıtlı bir işlev çağırır `terminate`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
