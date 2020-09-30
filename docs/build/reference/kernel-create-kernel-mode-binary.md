---
title: /kernel (Çekirdek modu ikilisi oluştur)
description: Microsoft C/C++ derleyicisi, çekirdek modu yürütmesi için yapılar ve bağlantılar projelerini bağlar.
ms.date: 09/28/2020
f1_keywords:
- /kernel
- /kernel-
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
ms.openlocfilehash: 8a8c02a6f102a52afbc52c154ce215ede3f38f74
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509355"
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel (Çekirdek modu ikilisi oluştur)

Windows çekirdeğinde yürütülebilecek bir ikili oluşturur. Geçerli projedeki kod, çekirdek modunda çalışan koda özgü, Basitleştirilmiş bir C++ dil özellikleri kümesi kullanılarak derlenir ve bağlanır.

## <a name="syntax"></a>Sözdizimi

> **`/kernel`**

## <a name="remarks"></a>Açıklamalar

Seçeneği belirtildiğinde, **`/kernel`** derleyici ve bağlayıcıya, çekirdek modunda hangi dil özelliklerinin izin verilme hızını ve çekirdek modu C++ ' da benzersiz olan çalışma zamanı kararsızlığına engel olmak için yeterli ifade eden bir güce sahip olduğunuzdan emin olun. Çekirdek modunda kesintiye uğramayan C++ dil özelliklerinin kullanımını yasaklayarak yapılır. Derleyici, büyük olasılıkla kesintiye uğramayan ancak devre dışı bırakılabilecek C++ dil özellikleri için uyarılar üretir.

Bu **`/kernel`** seçenek, bir yapılandırmanın derleyici ve bağlayıcı aşamaları için geçerlidir ve proje düzeyinde ayarlanır. Derleyiciye, **`/kernel`** bağlantı kurulduktan sonra, sonuçta elde edilen Ikilinin Windows çekirdeğine yüklenmesi gerektiğini belirtmek için anahtarı geçirin. Derleyici, C++ dil özelliklerinin spektrumını çekirdekle uyumlu bir alt kümeyle daraltacaktır.

Aşağıdaki tabloda, belirtildiğinde derleyici davranışındaki değişiklikler listelenmiştir **`/kernel`** .

| Davranış türü | **`/kernel`** durum |
|--|--|
| C++ özel durum işleme | Devre dışı. **`throw`** Ve **`try`** anahtar kelimelerin tüm örnekleri bir derleyici hatası (özel durum belirtimi dışında) yayar `throw()` . **`/EH`** İçin, dışında hiçbir seçenek ile uyumlu değildir **`/kernel`** **`/EH-`** . |
| RTTı | Devre dışı. **`dynamic_cast`** **`typeid`** Statik olarak kullanılmadığı durumlar, ve anahtar kelimelerin tüm örnekleri bir derleyici hatası yayar **`dynamic_cast`** . |
| `new` ve `delete` | Ya da işlecini açıkça tanımlamanız `new()` gerekir `delete()` . Derleyici ve çalışma zamanı varsayılan bir tanım sağlamaz. |

Seçeneğini kullandığınızda özel çağırma kuralları, [`/GS`](gs-buffer-security-check.md) derleme seçeneği ve tüm iyileştirmelere izin verilir **`/kernel`** . İç hat, **`/kernel`** derleyici tarafından kabul edilecek semantiklerle büyük ölçüde etkilenmez. Satır içi niteleyicinin sağlandığından emin olmak istiyorsanız **`__forceinline`** , belirli bir işlevin satır içine alınamadığına bilmeniz için Uyarı [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) ' nin etkinleştirildiğinden emin olmanız gerekir **`__forceinline`** .

`#pragma`Bu seçeneği denetlemek için eşdeğer değildir.

Derleyici **`/kernel`** anahtarı geçtiğinde, adlı `_KERNEL_MODE` ve değeri **1**olan bir önişlemci makrosunu önceden tanımlar. Yürütme ortamının Kullanıcı modunda mı yoksa çekirdek modunda mı olduğunu temel alarak kodu koşullu olarak derlemek için bu makroyu kullanabilirsiniz. Örneğin, aşağıdaki kod, `MyNonPagedClass` sınıfın, çekirdek modu yürütmesi için derlendiğinde, disk belleğine alınamayan bellek segmentinde olması gerektiğini belirtir.

```cpp
#ifdef _KERNEL_MODE
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))
#else
#define NONPAGESECTION
#endif

class NONPAGESECTION MyNonPagedClass
{
   // ...
};
```

Aşağıdaki hedef mimari birleşimlerinden bazıları ve **`/arch`** seçeneği ile kullanılırken bir hata oluşturur **`/kernel`** :

- **`/arch:SSE`**,,, **`/arch:SSE2`** **`/arch:AVX`** **`/arch:AVX2`** ve **`/arch:AVX512`** x86 üzerinde desteklenmez. Yalnızca **`/arch:IA32`** **`/kernel`** x86 üzerinde ile desteklenir.

- **`/arch:AVX`**, **`/arch:AVX2`** , ve **`/arch:AVX512`** **`/kernel`** x64 üzerinde ile desteklenmez.

İle derleme **`/kernel`** de **`/kernel`** bağlayıcıya geçirilir. Seçeneğin bağlayıcı davranışını nasıl etkilediği aşağıda verilmiştir:

- Artımlı bağlama devre dışı bırakıldı. **`/incremental`** Komut satırına eklerseniz, bağlayıcı şu önemli hatayı yayar:

   **önemli hata LNK1295: '/ıNCREıNCRE' WITH '/KERNEL ' belirtimiyle uyumlu değil; '/ıNCREıNCRE' olmadan bağla**

- Bağlayıcı, her nesne dosyasını (veya statik kitaplıklardan eklenen herhangi bir arşiv üyesini) inceleyerek seçeneği kullanılarak derlenip derlenmediğini denetler **`/kernel`** . Herhangi bir örnek bu ölçütü karşılıyorsa, bağlayıcı yine de başarılı bir şekilde bağlanır, ancak aşağıdaki tabloda gösterildiği gibi bir uyarı verebilir.

   | Komut | **`/kernel`** nesnesi | obj olmayan **`/kernel`** , Masz obj veya cvtres obj | **`/kernel`** Ve yapan olmayan karıştırma **`/kernel`** |
   |--|--|--|--|
   | **`link /kernel`** | Yes | Yes | Uyarı LNK4257 ile Evet |
   | **`link`** | Yes | Yes | Yes |

   **LNK4257 bağlama nesnesi/KERNEL ile derlenmedi; görüntü çalışmayabilir**

**`/kernel`** Seçeneği ve **`/driver`** seçeneği bağımsız olarak çalışır. Bunların birbirini hiçbir etkisi yoktur.

### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>Visual Studio 'da/Kernel derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusunda, ekleyin *`/kernel`* . Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
