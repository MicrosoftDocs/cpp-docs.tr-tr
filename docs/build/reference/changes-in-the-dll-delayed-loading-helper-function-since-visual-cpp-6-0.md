---
title: Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: cd6e842fd6d35e05f2d5a9f906713f0d85d3b80d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294635"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 Sonrasındaki Gecikmeli Yükleme Yardımcısı İşlevi DLL Değişiklikleri

Bilgisayarınızda Visual C++ birden fazla sürümü varsa veya kendi yardımcı işlevinizi tanımlanmışsa tarafından etkilenebilir DLL'ye yapılan değişiklikler Gecikmeli Yükleme Yardımcısı işlevi. Örneğin:

- **__delayLoadHelper** artık **__delayLoadHelper2**

- **__pfnDliNotifyHook** artık **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** artık **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** artık **__FUnloadDelayLoadedDLL2**

> [!NOTE]
>  Varsayılan yardımcı işlevini kullanıyorsanız, bu değişiklikler, etkilemez. Nasıl bağlayıcı çağırmayı ile ilgili bir değişiklik bulunmamaktadır.

## <a name="multiple-versions-of-visual-c"></a>Visual C++ birden çok sürümü

Bilgisayarınızda Visual C++ birden fazla sürümü varsa, bağlayıcı delayimp.lib eşleştiğinden emin olun. Yoksa uyuşmazlık ya da raporlama bir bağlayıcı hatası alırsınız `___delayLoadHelper2@8` veya `___delayLoadHelper@8` bir çözümlenmemiş dış sembol olarak. Eski bir eski delayimp.lib ile yeni bir bağlayıcı anlamına gelir ve eski bir bağlayıcı ile yeni bir delayimp.lib ikinci anlamına gelir.

Çözümlenmemiş bağlayıcı hata alırsanız, çalıştırma [dumpbin /linkermember](linkermember.md): hangi yardımcı işlevini yerine tanımlanan görmek için yardımcı işlevini içerecek şekilde beklediğiniz delayimp.lib 1. Yardımcı işlevini de bir nesne dosyasında tanımlanmış olması; çalıştırma [dumpbin /symbols](symbols.md) ve Ara `delayLoadHelper(2)`.

Biliyorsanız, Visual C++ 6.0 bağlayıcı ardından vardır:

- DUMPBIN tanımlar olup olmadığını belirlemek için gecikme yük yardımcı .lib veya .obj dosyası üzerinde çalıştırma **__delayLoadHelper2**. Aksi halde bağlantı başarısız olur.

- Tanımlama **__delayLoadHelper** gecikmeyi yardımcının .lib veya .obj dosyası yüklenemiyor.

## <a name="user-defined-helper-function"></a>Kullanıcı tanımlı yardımcı işlevi

Kendi yardımcı işlevinizi tanımlanan ve Visual C++'ın geçerli sürümü kullanıyorsanız, aşağıdakileri yapın:

- Yeniden adlandırmak için yardımcı işlevini **__delayLoadHelper2**.

- İşaretçiler (ImgDelayDescr delayimp.h içinde) gecikme tanımlayıcısındaki göreli adreslerine (RVA) hem 32 ve 64 bit programlarında beklendiği şekilde çalışması için mutlak adreslerden (VAs) değiştirilmiş olduğundan, bu geri Dönüştür işlemi işaretçileri gerekir. Yeni bir işlev eklendi: PFromRva delayhlp.cpp içinde bulunamadı. Bunları ya da 32 veya 64 bit işaretçiler için geri dönüştürmek için her tanımlayıcı alan bu işlevi kullanabilirsiniz. Varsayılan gecikme yük yardımcı işlevinizi örnek olarak kullanmak iyi bir şablon olmaya devam eder.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli yüklenen DLL için tüm içe aktarmaları yükleme

Bağlayıcı Gecikmeli yüklendi olarak belirtilen bir DLL'den tüm içe aktarmaları yükleyebilirsiniz. Bkz: [yükleniyor tüm içe aktarmaları Delay-Loaded DLL için](loading-all-imports-for-a-delay-loaded-dll.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı İşlevini Anlama](understanding-the-helper-function.md)
