---
title: code_seg (__declspec) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: code_seg_cpp
dev_langs: C++
helpviewer_keywords: code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1e222e3fb78807f4c67c746677e1223c7776a41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="codeseg-declspec"></a>code_seg (__declspec)
**Microsoft özel**  
  
 `code_seg` Bildirimi öznitelik adları sınıf üyesi işlevleri ve işlev için nesne kodu depolanacağı .obj dosyasında bir yürütülebilir metin kesimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `__declspec(code_seg(...))` Özniteliği kod yerleştirme, disk belleği veya ayrı ayrı bellekte kilitlenmiş bölümlerinden adlı ayrı sağlar. Örneklenmiş şablonların ve derleyicinin ürettiği kodun yerleşimini denetlemek için bu özniteliği kullanabilirsiniz.  
  
 A *segment* adlandırılmış bir birim olarak belleğe yüklenmiş bir .obj dosyasında veri bloğudur. A *metin segment* yürütülebilir kod içeren bir kesim. Terim *bölüm* kesimle genellikle birbirinin yerine kullanılır.  
  
 Nesne ne zaman üretti kod `declarator` tanımlanan tarafından belirtilen metin kesim koymak `segname`, dar harflerden olduğu. Adı `segname` içinde belirtilmesi gerekmez bir [bölüm](../preprocessor/section.md) bir bildiriminde kullanılmadan önce pragması. Varsayılan olarak, durumlarda `code_seg` belirtilirse, nesne kodu .text adlı bir segmente yerleştirin. A `code_seg` özniteliği geçersiz kılar var olan [#pragma code_seg](../preprocessor/code-seg.md) yönergesi. A `code_seg` herhangi bir üye işlevine uygulanan özniteliği geçersiz kılar `code_seg` kapsayan sınıfına uygulanan öznitelik.  
  
 Bir varlık varsa bir `code_seg` özniteliği, tüm bildirimler ve tanımlar aynı varlık olmalıdır aynı `code_seg` öznitelikleri. Bir temel sınıf varsa bir `code_seg` özniteliği, türetilmiş sınıfları aynı özniteliğe sahip olması gerekir.  
  
 Zaman bir `code_seg` özniteliği bir ad alanı kapsamı işlev veya üye işlevi uygulandığında, bu işlevin nesne kodu belirtilen metnin segment konur. Bu öznitelik bir sınıfa uygulandığında, sınıfın ve iç içe sınıfların tüm üye işlevleri, buna derleyici tarafından oluşturulan özel üye işlevleri de dahildir, belirtilen segmente yerleştirilir. Sınıfları'yerel olarak tanımlanan — Örneğin, bir üye işlev gövdesi içinde tanımlanan sınıflar — devralmaz `code_seg` çevreleyen kapsamdaki özniteliğidir.  
  
 Zaman bir `code_seg` özniteliği için bir şablon sınıfı veya şablon işlevi uygulandığında, şablonun tüm örtük özelleştirmeleri belirtilen kesimi yerleştirilir. Devralmaz açık ya da kısmi özelleştirmeleri `code_seg` birincil şablondan özniteliği. Aynı veya farklı bir belirtebilir `code_seg` uzmanlık özniteliği. A `code_seg` özniteliği için bir açık şablonu örneklemesi uygulanamaz.  
  
 Varsayılan olarak, derleyicinin ürettiği özel üye işlevi gibi bir kod bir .text segmente yerleştirilir. `#pragma code_seg` Yönergesi bu varsayılanı geçersiz değil. Kullanım `code_seg` sınıfı, sınıf şablonu veya nerede derleyici tarafından üretilen kod put denetimi işlevi şablonuna özniteliği.  
  
 Lambda'lar devralmak `code_seg` kapsayan kapsamlarına öznitelikleri. Bir kesim için bir lambda belirtmek için geçerli bir `code_seg` öznitelik parametre bildirimi yan tümcesi sonra ve herhangi önce değişebilir veya özel durum belirtimi, tüm izleyen dönüş türü belirtimi ve lambda gövdesi. Daha fazla bilgi için bkz: [Lambda ifadesi sözdizimi](../cpp/lambda-expression-syntax.md). Bu örnek, PagedMem adlı bir segmentte bir lambda tanımlar:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Farklı segmentlere özel üye işlevleri, özellikle sanal üye işlevleri, yerleştirirken dikkatli olun. Bir temel sınıf yöntemi disk belleksiz bir segmente bulunduğunda, disk bellekli bir segmentte bulunan türetilmiş bir sınıfta sanal bir işlev tanımlarsanız, diğer temel sınıf yöntemleri veya kullanıcı kodu sanal yöntemin çağrılmasının bir sayfa hatasını tetikleyeceğini varsayabilir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte gösterilir nasıl bir `code_seg` özniteliği denetimleri yerleştirme örtük zaman segmentlere ayırmak ve açık şablon uzmanlık kullanılır:  
  
```  
// code_seg.cpp  
// Compile: cl /EHsc /W4 code_seg.cpp  
  
// Base template places object code in Segment_1 segment  
template<class T>  
class __declspec(code_seg("Segment_1")) Example  
{  
public:  
   virtual void VirtualMemberFunction(T /*arg*/) {}  
};  
  
// bool specialization places code in default .text segment  
template<>  
class Example<bool>   
{  
public:  
   virtual void VirtualMemberFunction(bool /*arg*/) {}  
};  
  
// int specialization places code in Segment_2 segment  
template<>  
class __declspec(code_seg("Segment_2")) Example<int>   
{  
public:  
   virtual void VirtualMemberFunction(int /*arg*/) {}  
};  
  
// Compiler warns and ignores __declspec(code_seg("Segment_3"))  
// in this explicit specialization  
__declspec(code_seg("Segment_3")) Example<short>; // C4071  
  
int main()  
{  
   // implicit double specialization uses base template's  
   // __declspec(code_seg("Segment_1")) to place object code  
   Example<double> doubleExample{};  
   doubleExample.VirtualMemberFunction(3.14L);  
  
   // bool specialization places object code in default .text segment  
   Example<bool> boolExample{};  
   boolExample.VirtualMemberFunction(true);  
  
   // int specialization uses __declspec(code_seg("Segment_2"))  
   // to place object code  
   Example<int> intExample{};  
   intExample.VirtualMemberFunction(42);  
}  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)