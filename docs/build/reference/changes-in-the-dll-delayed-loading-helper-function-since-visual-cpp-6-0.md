---
title: Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: 536729e27c89d068957ea451355957e4a35348ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320606"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri

Bilgisayarınızda Visual C++'nin birden çok sürümü varsa veya kendi yardımcı işlevinizi tanımladıysanız, DLL gecikmiş yükleme yardımcı işlevinde yapılan değişikliklerden etkilenebilir. Örneğin:

- **__delayLoadHelper** şimdi **__delayLoadHelper2**

- **__pfnDliNotifyHook** şimdi **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** şimdi **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** şimdi **__FUnloadDelayLoadedDLL2**

> [!NOTE]
> Varsayılan yardımcı işlevini kullanıyorsanız, bu değişiklikler sizi etkilemez. Bağlayıcıyı nasıl çağırdığınıza ilişkin bir değişiklik yoktur.

## <a name="multiple-versions-of-visual-c"></a>Visual C++ birden fazla sürümü

Bilgisayarınızda Visual C++'ın birden çok sürümü varsa, bağlantı nın delayimp.lib ile eşleştiğinden emin olun. Bir uyuşmazlık varsa, bir bağlayıcı hata raporlama ya `___delayLoadHelper2@8` da `___delayLoadHelper@8` çözülmemiş bir dış simge olarak alırsınız. Eski eski bir delayimp.lib ile yeni bir bağlayıcı anlamına gelir, ve ikinci yeni bir delayimp.lib ile eski bir bağlayıcı anlamına gelir.

Çözülmemiş bir bağlayıcı hatası alırsanız, yerine hangi yardımcı işlevin tanımlandığını görmek için yardımcı işlevi içermesini beklediğiniz delayimp.lib'de [dumpbin /linkermember](linkermember.md):1'i çalıştırın. Yardımcı işlev bir nesne dosyasında da tanımlanabilir; [çöp /semboller](symbols.md) çalıştırmak ve `delayLoadHelper(2)`arayın.

Visual C++ 6.0 bağlantınız olduğunu biliyorsanız, aşağıdakileri

- **__delayLoadHelper2**tanımlayıp tanımlamadığını belirlemek için gecikme yükü yardımcısının .lib veya .obj dosyasında çöp lüğü çalıştırın. Değilse, bağlantı başarısız olur.

- Gecikme yükü yardımcısının .lib veya .obj dosyasındaki **__delayLoadHelper** tanımlayın.

## <a name="user-defined-helper-function"></a>Kullanıcı Tanımlı Yardımcı İşlevi

Kendi yardımcı işlevinizi tanımladıysanız ve Visual C++'ın geçerli sürümünü kullanıyorsanız, aşağıdakileri yapın:

- Yardımcı işlevi **__delayLoadHelper2**yeniden adlandırın.

- Gecikme tanımlayıcısındaki işaretçiler (Delayimp.h'deki ImgDelayDescr) mutlak adreslerden (VAs) göreli adreslerden (RVA) 32 ve 64 bit programlarda beklendiği gibi çalışmaya değiştirildiklerinden, bunları işaretçilere dönüştürmeniz gerekir. Yeni bir fonksiyon tanıtıldı: PFromRva, delayhlp.cpp bulundu. Bu işlevi tanımlayıcıdaki her alanda 32 veya 64 bit işaretçiye dönüştürmek için kullanabilirsiniz. Varsayılan gecikme yükü yardımcı işlevi örnek olarak kullanmak için iyi bir şablon olmaya devam eder.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Gecikme Yüklü DLL Için Tüm İthalatları Yükleyin

Bağlayıcı, gecikme yüklenmesi için belirttiğiniz bir DLL'den tüm içeri aktarımları yükleyebilir. Daha fazla bilgi [için Gecikme Yüklü DLL için Tüm İçiMeLer Yükleme'ye](loading-all-imports-for-a-delay-loaded-dll.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı İşlevini Anlama](understanding-the-helper-function.md)
