---
description: 'Hakkında daha fazla bilgi edinin: Visual C++ 6,0 sonrasında DLL Gecikmeli Yükleme Yardımcısı Işlevinde yapılan değişiklikler'
title: Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: 0141467aab0b804cf82d21c15510d8f9941853a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182495"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri

Bilgisayarınızda Visual C++ birden çok sürümü varsa veya kendi yardımcı işlevinizi tanımladıysanız, DLL Gecikmeli Yükleme Yardımcısı işlevinde yapılan değişikliklerden etkileniyor olabilirsiniz. Örneğin:

- **__delayLoadHelper** artık **__delayLoadHelper2**

- **__pfnDliNotifyHook** artık **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** artık **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** artık **__FUnloadDelayLoadedDLL2**

> [!NOTE]
> Varsayılan yardımcı işlevi kullanıyorsanız, bu değişiklikler sizi etkilemez. Bağlayıcıyı çağırma ile ilgili herhangi bir değişiklik yoktur.

## <a name="multiple-versions-of-visual-c"></a>Visual C++ birden çok sürümü

Bilgisayarınızda Visual C++ birden fazla sürümüne sahipseniz, bağlayıcının delayimp. lib ile eşleştiğinden emin olun. Bir uyuşmazlık varsa, ya da `___delayLoadHelper2@8` `___delayLoadHelper@8` çözümlenmemiş dış sembol olarak bir bağlayıcı hata bildirimi alırsınız. İlki eski bir delayimp. lib ile yeni bir bağlayıcı ifade, ikincisi ise yeni bir delayimp. lib ile eski bir bağlayıcı gerektirir.

Çözümlenmemiş bir bağlayıcı hatası alırsanız, bunun yerine hangi yardımcı işlevin tanımlandığını görmek için yardımcı işlev içermesini beklediğinizi delayimp. lib dosyasında [dumpbin/linkermember](linkermember.md): 1 ' i çalıştırın. Yardımcı işlevi bir nesne dosyasında da tanımlanabilir; [dumpbin/Symbols](symbols.md) komutunu çalıştırın ve öğesini arayın `delayLoadHelper(2)` .

Visual C++ 6,0 bağlayıcıya sahip olduğunuzu biliyorsanız:

- **__DelayLoadHelper2** tanımlamadığını öğrenmek için Gecikmeli yük Yardımcısı 'nın. lib veya. obj dosyasında dumpbin dosyasını çalıştırın. Aksi takdirde bağlantı başarısız olur.

- Gecikme Yükleme Yardımcısı 'nın. lib veya. obj dosyasında **__delayLoadHelper** tanımlayın.

## <a name="user-defined-helper-function"></a>User-Defined yardımcı Işlevi

Kendi yardımcı işlevinizi tanımladınız ve geçerli Visual C++ sürümünü kullanıyorsanız şunları yapın:

- Yardımcı işlevini **__delayLoadHelper2** olarak yeniden adlandırın.

- Gecikmeli Tanımlayıcıdaki işaretçiler (delayimp. h içinde ImgDelayDescr), hem 32 hem de 64 bit programlarda beklenen şekilde çalışmak üzere mutlak adreslerden (VAs) göreli adreslere (RVA) değiştiği için, bunları işaretçilere geri dönüştürmeniz gerekir. Yeni bir işlev sunulmuştur: delayhlp. cpp içinde bulunan PFromRva. Bu işlevi, Tanımlayıcıdaki her bir alanın 32 veya 64 bit işaretçilerine geri dönüştürmek için kullanabilirsiniz. Varsayılan Gecikmeli Yükleme Yardımcısı işlevi, örnek olarak kullanılacak iyi bir şablon olmaya devam eder.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Delay-Loaded DLL için tüm Içeri aktarmaları yükle

Bağlayıcı, belirttiğiniz DLL 'den gelen tüm içeri aktarımları Gecikmeli yükleme olarak yükleyebilir. Daha fazla bilgi için [bir Delay-Loaded dll Için tüm Içeri aktarmaları yükleme](loading-all-imports-for-a-delay-loaded-dll.md) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı Işlevini anlama](understanding-the-helper-function.md)
