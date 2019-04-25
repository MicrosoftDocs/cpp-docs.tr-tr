---
title: /kernel (Çekirdek Modu İkilisi Oluştur)
ms.date: 11/04/2016
f1_keywords:
- /kernel
- /kernel-
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
ms.openlocfilehash: d065364cf6d3ae824098634c070f3651324aa52a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291346"
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel (Çekirdek Modu İkilisi Oluştur)

Windows çekirdeğinde yürütülebilecek bir ikili oluşturur.

## <a name="syntax"></a>Sözdizimi

```
/kernel[-]
```

## <a name="arguments"></a>Arguments

**/ Kernel**<br/>
Geçerli projede kod derlenmiş ve çekirdek modunda çalışacak kodu özgü C++ dil kuralları kümesi kullanarak bağlı.

**/Kernel-**<br/>
Geçerli projede kod derlenmiş ve çekirdek modunda çalışacak kodu özgü C++ dil kuralları kullanmadan bağlı.

## <a name="remarks"></a>Açıklamalar

Var olan hiçbir `#pragma` eşdeğer bu seçimi denetlemek için.

Belirtme **/Kernel** seçeneği söyler derleyicide ve bağlayıcıda hangi dil özellikleri çekirdek modunda izin verilen yönetmeye kalkarsa ve için benzersiz olan çalışma zamanı kararsızlığı engellemek için yeterli etkileyici gücüyle sahip olduğunuzdan emin olun Çekirdek modu C++. Bu, çekirdek modunda kesintiye uğratıp C++ dil özelliklerinin kullanımını yasaklanması ve Uyarılar için olası kesintiye ancak devre dışı bırakılamaz, C++ dil özellikleri sağlayarak gerçekleştirilir.

**/Kernel** seçeneği bir derleme derleyici ve bağlayıcı aşamaları için geçerlidir ve proje düzeyinde ayarlanır. Geçirmek **/Kernel** derleyiciye elde edilen ikili bağladıktan sonra Windows çekirdeğe yükleneceğini göstermek için anahtar. Derleyici, çekirdek ile uyumlu olan bir alt kümesi için C++ dil özelliklerinin spektrumun sınırlar.

Aşağıdaki tabloda derleyici davranışında değişiklik olduğunda **/Kernel** belirtilir.

|Davranış türü|**/ Kernel** davranışı|
|-------------------|---------------------------|
|C++ Özel Durum İşleme|Devre dışı. Tüm örneklerini `throw` ve `try` anahtar sözcükler, bir derleyici hatası yayma (özel durum belirtimi dışında `throw()`). Hayır **/EH** seçenekleri ile uyumludur **/Kernel**, dışında **/EH-**.|
|RTTI|Devre dışı. Tüm örneklerini `dynamic_cast` ve `typeid` anahtar sözcükler, bir derleyici hatası sürece yayma `dynamic_cast` statik olarak kullanılır.|
|`new` ve `delete`|Açıkça tanımlamanız gerekir `new()` veya `delete()` işleci; derleyici ne çalışma zamanı varsayılan bir tanım sağlamanız.|

Çağırma kuralları, özel [/GS](gs-buffer-security-check.md) derleme seçeneği ve tüm iyileştirmeler kullandığınızda verilen **/Kernel** seçeneği. Satır içi kullanım büyük ölçüde etkilenmez tarafından **/Kernel**, derleyici tarafından kabul aynı semantiğe sahip. Emin olmak istiyorsanız `__forceinline` inlining'i niteleyicisi dikkate alınır, bu uyarı emin olun [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) belirli bir zaman öğrenmek için etkin `__forceinline` işlevi satır içine alınmış değil.

Derleyici geçirilen zaman **/Kernel** anahtarı, bunu önceden belirler adlı önişlemci makrosu `_KERNEL_MODE` ve değere sahip **1**. Kod yürütme ortamı kullanıcı modunda veya çekirdek modunda olduğuna göre koşullu olarak derlemek için bunu kullanabilirsiniz. Örneğin, aşağıdaki kodu, çekirdek modu yürütme için derlendiğinde sınıfı alınamayan bellek segmentinde olması gerektiğini belirtir.

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

Bazı hedef mimarisinin aşağıdaki birleşimler ve **/arch** seçeneği ile kullanıldığında bir hata oluşturmak **/Kernel**:

- **/ arch: {SSE&#124;SSE2&#124;AVX}** x86 üzerinde desteklenmez. Yalnızca **/arch:IA32** ile desteklenen **/Kernel** x86.

- **/ arch:** desteklenmeyen **/Kernel** x64.

İle oluşturma **/Kernel** ayrıca geçirir **/Kernel** bağlayıcıya. Her bağlayıcı davranışı bunun nasıl etkilediği şöyledir:

- Artımlı bağlamayı devre dışı bırakıldı. Eklerseniz **/ Incremental** komut satırına, bağlayıcı bu önemli bir hata verir:

   **BAĞLANTI: önemli hata LNK1295: '/ INCREMENTAL' ile uyumlu değil ' / çekirdek ' belirtimi; '/ INCREMENTAL' olmadan bağlayın**

- Bunu kullanarak derlenen olup olmadığını görmek için her nesne dosyası (veya herhangi bir eklenen arşiv üyesi statik kitaplıklarından) bağlayıcı inceler **/Kernel** seçeneği ancak değildi. Herhangi bir örneği, bu ölçütü karşılaması durumunda bağlayıcı yine de başarılı bir şekilde bağlar ancak aşağıdaki tabloda gösterildiği gibi bir uyarı, sorunu.

   ||**/ Kernel** obj|**/Kernel-** obj, MASM obj veya cvtresed|Karışık **/Kernel** ve **/kernel-** objs|
   |-|----------------------|-----------------------------------------------|-------------------------------------------------|
   |**bağlantı/Kernel**|Evet|Evet|Uyarıyla LNK4257 Evet|
   |**Bağlantı**|Evet|Evet|Evet|

   **LNK4257 bağlama nesnesi/Kernel ile derlenmemiş; Görüntü çalışmayabilir**

**/Kernel** seçeneği ve **Driver/Driver** seçeneği bağımsız olarak çalışır ve diğer ne etkiler.

### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>/ Kernel derleyici seçeneğini Visual Studio'da ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda `/kernel` veya `/kernel-`.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
