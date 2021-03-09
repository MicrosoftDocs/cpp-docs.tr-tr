---
title: Addresstemizleme gölge baytları
description: Derleyici tarafından üretilen kod ve Addresstemizleyerek çalışma zamanı tarafından yazılan ve okunan gölge baytların teknik açıklaması.
ms.date: 03/02/2021
helpviewer_keywords:
- Shadow bytes
- AddressSanitizer shadow bytes
- Address Sanitizer shadow bytes
- ASan shadow bytes
ms.openlocfilehash: 89c3051d2e68d579f2f187fcd12b45ff52cd8a58
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470713"
---
# <a name="addresssanitizer-shadow-bytes"></a>Addresstemizleme gölge baytları

Gölge bayt kavramını ve bunların çalışma zamanı uygulamasının nasıl kullanılabileceğini kısaca özetler [`/fsanitize=address`](../build/reference/fsanitize.md) . Daha ayrıntılı bilgi için, [yayma kağıdına](https://www.usenix.org/system/files/conference/atc12/atc12-final39.pdf) ve [addresstemizleme algoritmasına](https://github.com/google/sanitizers/wiki/AddressSanitizerAlgorithm)başvuracağız.

## <a name="core-concept"></a>Temel kavram

Uygulamanızın sanal adres alanındaki **8 baytın** her **biri bir gölge bayt** kullanılarak açıklanabilir.

Bir gölge bayt şu anda kaç baytlık erişilebilir olduğunu tanımlar:

- 0, tüm 8 bayt anlamına gelir
- 1-7 bir ile yedi bayt arasında bir anlamına gelir
- Negatif sayılar, raporlama tanılaması için kullanılacak çalışma zamanının bağlamını kodluyor.

### <a name="shadow-byte-legend"></a>Gölge bayt göstergesi

Tüm negatif sayıların tanımlandığı gölge bayt göstergesini göz önünde bulundurun:

:::image type="content" source="./media/asan-shadow-byte-legend.png" alt-text="Addresstemizleme gölge-bayt göstergesinin ekran görüntüsü.":::

## <a name="mapping---describing-your-address-space"></a>Eşleme-adres alanınızı açıklama

Uygulamanın "0-mod-8" hizalı sanal adres alanındaki her 8 bayt, sanal adres alanındaki bu yuvayı açıklayan gölge bayta eşleştirilebilir.  Bu eşleme, **basit bir kaydırma ve ekleme** ile gerçekleştirilebilir.

X86 üzerinde:

```cpp
char shadow_byte_value = *((Your_Address >> 3) + 0x30000000)
```

X64 üzerinde:

```cpp
char shadow_byte_value = *((Your_Address >> 3) + _asan_runtime_assigned_offset)
```

## <a name="code-generation---tests"></a>Kod oluşturma-testler

Derleyicinin ürettiği kod, statik veriler veya çalışma zamanı tarafından belirli gölge baytlarının nasıl yazılabileceğini düşünün. Bu sahte kod, herhangi bir yük veya mağazadan önce gelen bir denetimin nasıl üretibileceği gösterilmektedir:

```cpp
ShadowAddr = (Addr >> 3) + Offset;
if (*ShadowAddr != 0) {
    ReportAndCrash(Addr);
}
```

8 bayttan daha az bir bellek başvurusu düzenlenirken, izleme biraz daha karmaşıktır. Gölge değer pozitifse (yani yalnızca 8 baytlık sözcükteki ilk k baytına erişilebiliyorsa), adresin son 3 bitini k ile karşılaştırmanız gerekir.

```cpp
ShadowAddr = (Addr >> 3) + Offset;
k = *ShadowAddr;
if (k != 0 && ((Addr & 7) + AccessSize > k)) {
    ReportAndCrash(Addr);
}
```

Çalışma zamanı ve derleyicinin ürettiği kod, her ikisi de gölge bayt yazın. Bu gölge baytlar, kapsamlar sona veya depolama serbest bırakıldığında erişime izin verir veya erişimi iptal eder. Uygulamanın adres alanındaki 8 baytlık "Yuvaları", programın yürütülmesine belirli bir zamanda tanımlayan gölge bayt okuma üzerindeki denetim. Açıkça oluşturulan bu denetimlerin yanı sıra, çalışma zamanı, CRT 'daki çok sayıda işlevi geçtikten sonra gölge baytları de denetler (veya "kancalar").

Daha fazla bilgi için, ele [geçirilebilecek işlevler](./asan-runtime.md#default-interceptors)listesine bakın.

## <a name="setting-shadow-bytes"></a>Gölge baytlar ayarlanıyor

Hem derleyicinin oluşturduğu kod hem de Addresstemizme çalışma zamanı gölge baytlar yazabilir. Örneğin, derleyici bir iç kapsamda tanımlanan yığın Yereller için sabit boyutlu erişime izin verecek şekilde gölge baytlar ayarlayabilir. Çalışma zamanı, veri bölümündeki genel değişkenleri gölge bayt ile çevrelendirebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
