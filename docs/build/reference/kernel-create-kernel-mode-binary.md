---
title: /kernel (Çekirdek Modu İkilisi Oluştur)
ms.date: 11/04/2016
f1_keywords:
- /kernel
- /kernel-
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
ms.openlocfilehash: bcef52144e4da932e9e1b6acbcd5f2170c4c7f86
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211950"
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel (Çekirdek Modu İkilisi Oluştur)

Windows çekirdeğinde yürütülebilecek bir ikili oluşturur.

## <a name="syntax"></a>Söz dizimi

```
/kernel[-]
```

## <a name="arguments"></a>Bağımsız değişkenler

**/Kernel**<br/>
Geçerli projedeki kod, çekirdek modunda çalışacak koda özgü bir C++ dil kuralları kümesi kullanılarak derlenir ve bağlanır.

**/Kernel**<br/>
Geçerli projedeki kod, çekirdek modunda çalışacak koda özgü C++ dili kuralları kullanılmadan derlenir ve bağlanır.

## <a name="remarks"></a>Açıklamalar

`#pragma`Bu seçeneği denetlemek için eşdeğer bir değer yoktur.

**/Kernel** seçeneğinin belirtilmesi, derleyiciye ve bağlayıcıya, çekirdek modunda hangi dil özelliklerinin kullanılabilir olduğunu ve çekirdek modu C++ ' da benzersiz olan çalışma zamanı kararsızlığına engel olmak için yeterli ifade gücüne sahip olduğunuzdan emin olmak için söyler. Bu, çekirdek modunda karışıklığa neden olan C++ dil özelliklerinin kullanımını ve potansiyel olarak kesintiye uğramayan ancak devre dışı bırakılamayan C++ dil özelliklerine yönelik uyarıları sağlayarak gerçekleştirilir.

**/Kernel** seçeneği, bir yapılandırmanın derleyici ve bağlayıcı aşamaları için geçerlidir ve proje düzeyinde ayarlanır. Derleyiciye, bağlantı kurulduktan sonra sonuçta elde edilen ikilinin Windows çekirdeğine yüklenmesi gerektiğini belirtmek için **/Kernel** anahtarını geçirin. Derleyici, C++ dil özelliklerinin spektrumını çekirdekle uyumlu bir alt kümeyle daraltacaktır.

Aşağıdaki tabloda, **/Kernel** belirtildiğinde derleyici davranışında yapılan değişiklikler listelenmiştir.

|Davranış türü|**/Kernel** Durum|
|-------------------|---------------------------|
|C++ Özel Durum İşleme|Devre dışı. **`throw`** Ve **`try`** anahtar kelimelerin tüm örnekleri bir derleyici hatası (özel durum belirtimi dışında) yayar `throw()` . **/EHI**dışında **/Kernel**ile uyumlu **/Eh** seçeneği yoktur.|
|RTTı|Devre dışı. **`dynamic_cast`** **`typeid`** Statik olarak kullanılmadığı durumlar, ve anahtar kelimelerin tüm örnekleri bir derleyici hatası yayar **`dynamic_cast`** .|
|`new` ve `delete`|Ya da işlecini açıkça tanımlamanız `new()` gerekir `delete()` ; ne derleyici ne de çalışma zamanı varsayılan bir tanım sağlar.|

Özel çağırma kuralları, [/GS](gs-buffer-security-check.md) Build seçeneği ve **/Kernel** seçeneğini kullandığınızda tüm iyileştirmelere izin verilir. İç hat, derleyicide büyük ölçüde **etkilenmez ve derleyici**tarafından kabul edilecek semantiklerle etkilenmez. Satır içi niteleyicinin sağlandığından emin olmak istiyorsanız **`__forceinline`** , belirli bir işlevin satır içine alınamadığına bilmeniz için Uyarı [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) ' nin etkinleştirildiğinden emin olmanız gerekir **`__forceinline`** .

Derleyici **/Kernel** anahtarını geçirildiğinde, adlı `_KERNEL_MODE` ve değeri **1**olan bir önişlemci makrosunu önceden tanımlar. Bu işlemi, yürütme ortamının Kullanıcı modunda mı yoksa çekirdek modunda mı olduğunu temel alarak kodu koşullu olarak derlemek için kullanabilirsiniz. Örneğin, aşağıdaki kod, sınıfın, çekirdek modu yürütmesi için derlendiğinde, disk belleğine alınamayan bellek segmentinde olması gerektiğini belirtir.

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

Hedef mimarinin ve **/Arch** seçeneğinin bazı aşağıdaki birleşimleri **/Kernel**ile kullanılırken bir hata üretir:

- **/Arch: {SSE&#124;SSE2&#124;AVX}** x86 üzerinde desteklenmez. Yalnızca **/Arch: IA32** x86 üzerinde **/Kernel** ile desteklenir.

- **/Arch: AVX** , x64 üzerinde **/Kernel** ile desteklenmez.

**/Kernel** ile derleme ayrıca bağlayıcıya **/Kernel** ' i geçirir. Bu, bağlayıcı davranışını nasıl etkiler:

- Artımlı bağlama devre dışı bırakıldı. Komut satırına **/ıncreül** eklerseniz bağlayıcı şu önemli hatayı yayar:

   **BAĞLANTı: önemli hata LNK1295: '/artımlı ' '/KERNEL ' belirtimiyle uyumlu değil; '/ıNCREıNCRE' olmadan bağla**

- Bağlayıcı, her nesne dosyasını (veya statik kitaplıklardan eklenen herhangi bir arşiv üyesini) inceleyerek, bu dosyanın **/Kernel** seçeneği kullanılarak derlenip derlenmeyeceğini görebilir. Herhangi bir örnek bu ölçütü karşılıyorsa, bağlayıcı yine de başarılı bir şekilde bağlanır, ancak aşağıdaki tabloda gösterildiği gibi bir uyarı verebilir.

   ||**/Kernel** obj|**/Kernel-** obj, ması obj veya cvtresed|**/Kernel** ve **/Kernel-** yapan karışımı|
   |-|----------------------|-----------------------------------------------|-------------------------------------------------|
   |**bağlantı/Kernel**|Yes|Yes|Uyarı LNK4257 ile Evet|
   |**bağlantısının**|Yes|Yes|Yes|

   **LNK4257 bağlama nesnesi/KERNEL ile derlenmedi; görüntü çalışmayabilir**

**/Kernel** seçeneği ve **/DRIVER** seçeneği bağımsız olarak çalışır ve bunun hiçbirini etkilemez.

### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>Visual Studio 'da/Kernel derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusunda, `/kernel` veya ekleyin `/kernel-` .

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
