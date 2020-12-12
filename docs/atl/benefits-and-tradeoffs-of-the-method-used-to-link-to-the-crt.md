---
description: "Daha fazla bilgi edinin: CRT 'a bağlamak için kullanılan metodun avantajları ve avantajları"
title: CRT 'a bağlamak için kullanılan metodun avantajları ve avantajları
ms.date: 05/06/2019
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: 763332de9615e978d84902f67f2c97efd0767c89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148531"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>CRT 'a bağlamak için kullanılan metodun avantajları ve avantajları

Projeniz, dinamik olarak ya da statik olarak CRT ile bağlanabilir. Aşağıdaki tabloda, hangi yöntemin kullanılacağını seçerken kullanılan avantajlar ve dengeler özetlenmektedir.

|Yöntem|Avantaj|Zorunluluğunu getirir|
|------------|-------------|--------------|
|CRT 'ye statik olarak bağlama<br /><br /> (**Çalışma zamanı kitaplığı** **tek iş parçacıklı** olarak ayarlandı)|Görüntünün çalışacağı sistemde CRT DLL gerekli değildir.|Yansımanıza yaklaşık 25K başlangıç kodu eklenir, boyutu önemli ölçüde arttırıyor.|
|CRT 'ye dinamik olarak bağlama<br /><br /> (**Çalışma zamanı kitaplığı** **çok iş parçacıklı** olarak ayarlandı)|Resminiz CRT başlangıç kodu gerektirmez, bu nedenle çok daha küçüktür.|CRT DLL, görüntüyü çalıştıran sistemde olmalıdır.|

[ATL PROJENIZDE CRT 'ye bağlama](../atl/linking-to-the-crt-in-your-atl-project.md) konusu konu, CRT ile bağlantı yapılacak şekilde nasıl seçim yapılacağını tartışır.

## <a name="see-also"></a>Ayrıca bkz.

[ATL ve C Run-Time kodla programlama](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md)<br/>
[CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)
