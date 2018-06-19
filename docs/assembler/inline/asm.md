---
title: __asm | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- __asm
- __asm_cpp
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], vs. asm blocks
- __asm keyword [C++]
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77e09f6af92839c6113c9c5ba375a1583bcf7149
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052683"
---
# <a name="asm"></a>__asm
**Microsoft özel**  
  
 `__asm` Anahtar sözcüğü satır içi derleyicisi çağırır ve yerde C veya C++ deyimi yasal görünebilir. Tek başına bulunamaz. Derleme yönerge, küme ayraçları veya, çok az içine yönergeleri grubu tarafından gelmelidir küme ayraçları boş bir çifti. Terim "`__asm` blok" Buraya herhangi bir yönerge veya desteklemediğini köşeli parantez içindeki yönergeleri grubu başvuruyor.  
  
> [!NOTE]
>  Standart C++ Visual C++ desteği `asm` derleyici anahtar sözcüğü bir hata oluşturmaz olgu için anahtar sözcüğü sınırlıdır. Ancak, bir `asm` bloğu değil anlamlı kod oluşturur. Kullanım `__asm` yerine `asm`.  
  
 Sözdizimi:  
  
 __asm *derleme yönergesi* [;]  
  
 __asm { *derleme yönerge listesi* } [;]  
  
## <a name="grammar"></a>Dilbilgisi  
 `__asm`  `assembly-instruction`  `;`İptal Et  
  
 `__asm {`  `assembly-instruction-list`  `};`İptal Et  
  
 *derleme yönerge listesi*:  
 `assembly-instruction` `;`İptal Et  
  
 `assembly-instruction` `;` `assembly-instruction-list` `;`İptal Et  
  
 Köşeli parantez kullanılırsa `__asm` anahtar sözcüğü anlamına gelir satırın geri kalanı bir derleme dili ifadesi olur. Köşeli parantez ile kullandıysanız, ayraçlar arasında her satır bir derleme dili bildirimi olduğu anlamına gelir. Önceki sürümlerle uyumluluk için `_asm` eşanlamlısı olduğu `__asm`.  
  
 Bu yana `__asm` anahtar sözcüğü bir deyim ayırıcı, aynı satırda derleme yönergeleri koyabilirsiniz.  
  
 Visual C++ 2005'ten önce yönergesi  
  
```  
__asm int 3  
```  
  
 Yerel kod ile derlendiğinde oluşturulmasına neden değil **/CLR**; bir CLR sonu yönergesi için yönerge derleyici çevrilir.  
  
 `__asm int 3` Yerel kod oluşturma işlevi için şimdi sonuçlanır. Bir işlevin kodunuzda bir kesme noktası neden ve MSIL için derlenmiş bu işlevin istiyorsanız kullanmak istiyorsanız [__debugbreak](../../intrinsics/debugbreak.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod parçası olan basit bir `__asm` ayraçlar içinde engelle:  
  
```  
__asm {  
   mov al, 2  
   mov dx, 0xD007  
   out dx, al  
}  
```  
  
 Alternatif olarak, koyabilirsiniz `__asm` her derleme yönergesi önünde:  
  
```  
__asm mov al, 2  
__asm mov dx, 0xD007  
__asm out dx, al  
```  
  
 Çünkü `__asm` anahtar sözcüğü bir deyim ayırıcı, derleme yönergeleri aynı satırda koyabilirsiniz:  
  
```  
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al  
```  
  
 Üç örnek ilk stili ancak aynı kodunu oluşturmak (kapsayan `__asm` ayraçlar içinde engelleme) bazı avantajları vardır. Küme ayraçları açıkça bütünleştirilmiş kodu C veya C++ kodunu ayırın ve gereksiz yinelenmesinin kaçının `__asm` anahtar sözcüğü. Küme ayraçları de belirsizlikleri engelleyebilirsiniz. C veya C++ deyimi aynı satır üzerinde koymak istiyorsanız bir `__asm` bloğu, blok küme ayraçları almalısınız. Küme ayraçları derleyici derleme kodu durur ve C veya C++ deyimleri nerede başlaması bildiremez. Son olarak, küme ayraçları metinde aynı normal MASM metin biçiminde olduğundan, kolayca Kes ve varolan MASM kaynak dosyaları metni yapıştırın.  
  
 C ve C++, kapsayan kaşlı ayraç aksine bir `__asm` blok değişken kapsamı etkilemez. Ayrıca geçirebilmenize `__asm` blokları; değişken kapsamı etkilememesi iç içe geçmiş yapar.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../../cpp/keywords-cpp.md)   
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)