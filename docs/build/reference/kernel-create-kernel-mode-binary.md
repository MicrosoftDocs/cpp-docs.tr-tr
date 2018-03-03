---
title: "-Çekirdek (çekirdek oluşturma modu ikili) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /kernel
- /kernel-
dev_langs:
- C++
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0e20df59788577acb680cbd18b737f7ec2d7822
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel (Çekirdek Modu İkilisi Oluştur)
Windows Çekirdeği'nde yürütülebilir bir ikili oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/kernel[-]  
```  
  
## <a name="arguments"></a>Arguments  
 **/ Kernel**  
 Geçerli projenin kod derlenmiş ve çekirdek modunda çalışacak kodu özgü C++ dili kuralları kümesi kullanarak bağlanır.  
  
 **/Kernel-**  
 Geçerli projenin kod derlenmiş ve çekirdek modunda çalışacak kodu özgü C++ dili kuralları kullanmadan bağlanır.  
  
## <a name="remarks"></a>Açıklamalar  
 Yoktur hiçbir `#pragma` bu seçenek denetim eşdeğerdir.  
  
 Belirtme **/Kernel** seçenek söyler derleyici ve bağlayıcı hangi dil özellikleri çekirdek modunda izin verilen sürdüremezse ve olduğu çalışma zamanı kararsızlığı engellemek için yeterli ifade gücüyle sahip olduğundan emin olun Çekirdek modu C++ benzersiz. Bu, çekirdek modunda dağıtıldığından C++ dil özellikleri kullanımını yasaklanması tarafından ve potansiyel olarak dağıtıldığından ancak devre dışı bırakılamaz C++ dil özellikleri için uyarılar sağlayarak gerçekleştirilir.  
  
 **/Kernel** seçeneği proje düzeyinde ayarlanır ve bir yapı derleyici ve bağlayıcı aşamaları için geçerlidir. Geçirmek **/Kernel** elde edilen ikili bağladıktan sonra Windows çekirdeğe yükleneceğini derleyiciye göstermek için anahtar. Derleyici C++ dil özellikleri çekirdek ile uyumlu olan bir alt yelpazesini daraltmak.  
  
 Derleyici davranışı değişiklikleri aşağıdaki tabloda, **/Kernel** belirtilir.  
  
|Davranış türü|**/ Kernel** davranışı|  
|-------------------|---------------------------|  
|C++ Özel Durum İşleme|Devre dışı. Tüm örneklerini `throw` ve `try` anahtar sözcükleri yayma derleyici hatası (özel durum belirtimi dışında `throw()`). Hayır **/EH** seçenekleri ile uyumlu **/Kernel**, dışında **/EH-**.|  
|RTTI|Devre dışı. Tüm örneklerini `dynamic_cast` ve `typeid` anahtar sözcükleri yayma derleyici hatası sürece `dynamic_cast` statik olarak kullanılır.|  
|`new`ve`delete`|Açıkça tanımlamalısınız `new()` veya `delete()` işleci; derleyici ne çalışma zamanı varsayılan tanımı tedarik.|  
  
 Çağırma kuralları, özel [/GS](../../build/reference/gs-buffer-security-check.md) derleme seçeneği ve tüm iyileştirmeler kullandığınızda verilen **/Kernel** seçeneği. Satır içi kullanım büyük ölçüde etkilenmez tarafından **/Kernel**, derleyici tarafından dikkate alınır aynı semantiği ile. Emin olmak istiyorsanız `__forceinline` satır içi kullanım niteleyicisi dikkate alınır, bu uyarı emin olun [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) belirli bir zaman bilmesi etkin `__forceinline` işlev satır içi değil.  
  
 Derleyici geçirilen zaman **/Kernel** anahtarı, bunu önceden belirler adlı bir önişlemci makrosu `_KERNEL_MODE` ve değerine sahip **1**. Koşullu yürütme ortamı kullanıcı modunda veya çekirdek modunda olduğuna bağlı olarak kod derlemek için bunu kullanabilirsiniz. Örneğin, aşağıdaki kod sınıfı için çekirdek modu yürütme derlendiğinde bir disk belleğine alınamayan bellek kesimdeki olması gerektiğini belirtir.  
  
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
  
 Bazı hedef mimari aşağıdaki birleşimlerini ve **/arch** seçeneği ile kullanıldığında bir hata üretmek **/Kernel**:  
  
-   **/ arch: {SSE &#124; SSE2 &#124; AVX}** x86 üzerinde desteklenmez. Yalnızca **/arch:IA32** ile desteklenen **/Kernel** x86 üzerinde.  
  
-   **/arch:AVX** desteklenmeyen **/Kernel** x64 üzerinde.  
  
 İle derleme **/Kernel** de geçirir **/Kernel** bağlayıcı için. Her bunun bağlayıcı davranışı nasıl etkilediği şöyledir:  
  
-   Artımlı bağlantılandırma devre dışı bırakılır. Eklerseniz **/ artımlı** komut satırına bağlayıcı bu önemli hatası yayar:  
  
     **BAĞLANTI: önemli bir hata LNK1295: '/ ARTIMLI' ile uyumlu değil ' / çekirdek ' belirtimi; Bağlantı '/ ARTIMLI' olmadan**  
  
-   Bunu kullanarak derlenmiştir olup olmadığını görmek için her nesne dosyası (veya herhangi bir statik kitaplıklarından birlikte arşiv üyesi) bağlayıcı inceler **/Kernel** seçeneği ancak değildi. Tüm örnekleri bu ölçüte uyan, bağlayıcı, yine de başarıyla bağlar ancak bir uyarı aşağıdaki tabloda gösterildiği gibi sorun.  
  
    ||**/ Kernel** obj|**/Kernel-** obj, MASM obj veya cvtresed|Karışık **/Kernel** ve **/kernel-** objs|  
    |-|----------------------|-----------------------------------------------|-------------------------------------------------|  
    |**bağlantı/Kernel**|Evet|Evet|LNK4257 uyarıyla Evet|  
    |**bağlantı**|Evet|Evet|Evet|  
  
     **/ Kernel ile derlenmemiş LNK4257 nesne; Görüntü çalışmayabilir**  
  
 **/Kernel** seçeneği ve **/sürücü** seçeneği bağımsız olarak çalışır ve ikisi diğer etkiler.  
  
### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>/ Kernel derleyici seçeneği Visual Studio'da ayarlamak için  
  
1.  Açık **özellik sayfaları** projesi için iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  İçinde **ek seçenekler** kutusunda, eklemek `/kernel` veya `/kernel-`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)