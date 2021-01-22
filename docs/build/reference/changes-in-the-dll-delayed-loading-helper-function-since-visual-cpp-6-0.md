---
description: 'Hakkında daha fazla bilgi edinin: Visual C++ 6,0 sonrasında DLL Gecikmeli Yükleme Yardımcısı işlevinde yapılan değişiklikler'
title: Visual C++ 6.0 sonrasındaki gecikmeli yükleme yardımcısı işlevi DLL değişiklikleri
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.openlocfilehash: a83d5e2895863efde396c48d68316e32aa42a2a1
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666972"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 sonrasındaki gecikmeli yükleme yardımcısı işlevi DLL değişiklikleri

Bilgisayarınızda Visual C++ birden çok sürümü varsa veya kendi yardımcı işlevinizi tanımladıysanız, DLL Gecikmeli Yükleme Yardımcısı işlevinde yapılan değişiklikler sizi etkileyebilir. Örnek:

- **`__delayLoadHelper`** Artık `__delayLoadHelper2`

- `__pfnDliNotifyHook` Artık `__pfnDliNotifyHook2`

- `__pfnDliFailureHook` Artık `__pfnDliFailureHook2`

- `__FUnloadDelayLoadedDLL` Artık `__FUnloadDelayLoadedDLL2`

> [!NOTE]
> Varsayılan yardımcı işlevi kullanıyorsanız, bu değişiklikler sizi etkilemez. Bağlayıcıyı çağırma ile ilgili herhangi bir değişiklik yoktur.

## <a name="multiple-versions-of-visual-c"></a>Visual C++ birden çok sürümü

Bilgisayarınızda Visual C++ birden fazla sürümüne sahipseniz, bağlayıcının eşleştiğinden emin olun *`delayimp.lib`* . Uyuşmazlık varsa, ya da `___delayLoadHelper2@8` `___delayLoadHelper@8` çözümlenmemiş dış sembol olarak bir bağlayıcı hata bildirimi alırsınız. İlki eski olan yeni bir bağlayıcı gerektirir *`delayimp.lib`* ve ikinci, yeni bir bağlayıcı olan eski bir bağlayıcı anlamına gelir *`delayimp.lib`* .

Çözümlenmemiş bir bağlayıcı hatası alırsanız, [`dumpbin /linkermember:1`](linkermember.md) *`delayimp.lib`* bunun yerine hangi yardımcı işlevin tanımlandığını görmek için yardımcı işlevi bulundurduğunuz üzerinde öğesini çalıştırın. Yardımcı işlevi bir nesne dosyasında da tanımlanabilir; öğesini çalıştırın [`dumpbin /symbols`](symbols.md) ve bulun `delayLoadHelper` `delayLoadHelper2` .

Visual C++ 6,0 bağlayıcıya sahip olduğunuzu biliyorsanız:

- **`dumpbin`** *`.lib`* *`.obj`* Tarafından tanımlanmadığını öğrenmek için Gecikmeli yük Yardımcısı ' nı veya dosyasını çalıştırın `__delayLoadHelper2` . Aksi takdirde bağlantı başarısız olur.

- `__delayLoadHelper`Gecikmeli yük Yardımcısı *`.lib`* veya *`.obj`* dosyasında tanımlayın.

## <a name="user-defined-helper-function"></a>Kullanıcı tanımlı yardımcı işlevi

Kendi yardımcı işlevinizi tanımladınız ve geçerli Visual C++ sürümünü kullanıyorsanız, aşağıdaki adımları uygulayın:

- Yardımcı işlevini olarak yeniden adlandırın `__delayLoadHelper2` .

- Gecikme Tanımlayıcıdaki işaretçiler ( `ImgDelayDescr` içindeki *`delayimp.h`* ), 32-bit ve 64 bit programlarında beklenen şekilde çalışmak üzere mutlak adreslerden (VAS) göreli adreslere (RVA) değiştiği için, bu RVA öğesini işaretçilere geri dönüştürmeniz gerekir. Yeni bir işlev tanıtılmıştır: `PFromRva` , içinde bulunan *`delayhlp.cpp`* . Bu işlevi, Tanımlayıcıdaki her bir alandan 32 bit ya da 64-bit işaretçilerine geri dönüştürmek için kullanabilirsiniz. Varsayılan Gecikmeli Yükleme Yardımcısı işlevi, örnek olarak kullanılacak iyi bir şablon olmaya devam eder.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli yüklenen DLL için tüm içeri aktarmaları yükle

Bağlayıcı, belirttiğiniz DLL 'den gelen tüm içeri aktarımları Gecikmeli yükleme olarak yükleyebilir. Daha fazla bilgi için bkz. [Gecikmeli yüklenen dll için tüm içeri aktarmaları yükleme](loading-all-imports-for-a-delay-loaded-dll.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı işlevini anlama](understanding-the-helper-function.md)
