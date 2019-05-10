---
title: Avantajlı ve Avantajsız yönleri CRT bağlantı için kullanılan yöntemi
ms.date: 05/06/2019
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: b2e504de91cea9fef6e9acb0fc851bc2cc271e97
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221272"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Avantajlı ve Avantajsız yönleri CRT bağlantı için kullanılan yöntemi

Proje, dinamik veya statik olarak CRT ile bağlayabilirsiniz. Aşağıdaki tabloda, avantajları ve hangi yöntemin kullanılacağını seçerken erişilen alışverişler özetlenmektedir.

|Yöntem|Faydası|Zorunluluğunu getirir|
|------------|-------------|--------------|
|Statik olarak CRT'ye bağlanma<br /><br /> (**Çalışma zamanı kitaplığı** kümesine **tek iş parçacıklı**)|CRT DLL görüntü çalıştıracağınız sisteminde gerekli değildir.|Yaklaşık 25K başlangıç kod boyutunu önemli ölçüde artırarak, görüntüye eklenir.|
|Dinamik olarak CRT'ye bağlanma<br /><br /> (**Çalışma zamanı kitaplığı** kümesine **çok iş parçacıklı**)|Çok daha küçük olacak şekilde görüntünüzü CRT başlatma kodunu gerektirmez.|CRT DLL görüntüsünü çalıştıran sistemde olması gerekir.|

Konu [CRT projenize ATL içinde bağlama](../atl/linking-to-the-crt-in-your-atl-project.md) seçin CRT'ye bağlanmak bir şekilde anlatılmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[ATL ve C Çalışma Zamanı Koduyla Programlama](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md)<br/>
[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
