---
title: code_seg (__declspec)
ms.date: 11/04/2016
f1_keywords:
- code_seg_cpp
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
ms.openlocfilehash: a0b9c6dcd7ee19af59ac39a71498fe41bfc107ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216560"
---
# <a name="codeseg-declspec"></a>code_seg (__declspec)

**Microsoft'a özgü**

**Code_seg** nesne kodu işlev veya sınıf üyesi işlevlerinin depolanacağı .obj dosyasına bir yürütülebilir metin segmentine bildirim öznitelik adları.

## <a name="syntax"></a>Sözdizimi

```
__declspec(code_seg("segname")) declarator
```

## <a name="remarks"></a>Açıklamalar

`__declspec(code_seg(...))` Özniteliği, kod yerleşiminin disk belleğine alınabilecek veya bellekte tek tek kilitli, kilitlenebilecek ayrı sağlar. Örneklenmiş şablonların ve derleyicinin ürettiği kodun yerleşimini denetlemek için bu özniteliği kullanabilirsiniz.

A *segment* belleğe bir birim olarak yüklenen .obj dosyasındaki verilerin adlandırılmış bir bloğudur. A *metin segmenti* yürütülebilir kod içeren bir segmenttir. Terim *bölümü* sıklıkla segment ile birbirinin yerine kullanılır.

Oluşturulan kod nesnesi `declarator` tanımlanan tarafından belirtilen metin segmentinde koymak `segname`, bir dar dize değişmez değeri olduğu. Adı `segname` belirtilmesi gerekmez bir [bölümü](../preprocessor/section.md) bir bildirimde kullanılabilmesi pragması. Varsayılan olarak hiçbir `code_seg` belirtilirse, nesne kodu .text adlı bir Segmentte koyun. A **code_seg** öznitelik geçersiz kılmalarını herhangi bir mevcut [#pragma code_seg](../preprocessor/code-seg.md) yönergesi. A **code_seg** herhangi bir üye işlevine uygulanan öznitelik geçersiz kılmalarını **code_seg** özniteliği kapsayan sınıfa uygulanır.

Varlığın varsa bir **code_seg** özniteliği, tüm bildirimlerinin ve tanımlarının aynı varlığın olmalıdır aynı **code_seg** öznitelikleri. Bir temel sınıf varsa bir **code_seg** özniteliği, türetilen sınıfların aynı özniteliğe sahip olması gerekir.

Olduğunda bir **code_seg** öznitelik ad alanı kapsamı işlevine veya bir üye işlevine uygulandığında, bu işlevin nesne kodu belirtilen metin segmentine yerleştirilir. Bu öznitelik bir sınıfa uygulandığında, sınıfın ve iç içe sınıfların tüm üye işlevleri, buna derleyici tarafından oluşturulan özel üye işlevleri de dahildir, belirtilen segmente yerleştirilir. Sınıflar'yerel olarak tanımlanan — Örneğin, bir üye işlev gövdesinde tanımlanmış sınıflar — devralmaz **code_seg** kapsayan kapsamın özniteliği.

Olduğunda bir **code_seg** öznitelik, bir şablon sınıfı veya şablon işlevine uygulandığında, şablonun tüm örtük uzmanlıkları belirtilen segmente yerleştirilir. Açık ya da kısmi uzmanlıklar devralmaz **code_seg** birincil şablondan gelen öznitelik. Aynı veya farklı bir belirtebilir **code_seg** uzmanlıkta özniteliği. A **code_seg** bir açık şablon örneklemesine uygulanamaz.

Varsayılan olarak, derleyicinin ürettiği özel üye işlevi gibi bir kod bir .text segmente yerleştirilir. `#pragma code_seg` Yönergesi bu varsayılanı Geçersiz Kılmıyor. Kullanım **code_seg** sınıfı, bir sınıf şablonunda ya da derleyicinin ürettiği kodun nereye yerleştirildiğini denetleyen şablon işlevinde özniteliği.

Lambdalar devral **code_seg** kapsayan kapsamından gelen öznitelikleri. Bir lambda için bir segment belirtmek için geçerli bir **code_seg** öznitelik parametre bildirimi yan tümcesinden sonra ve herhangi önce değişebilir veya özel durum belirtimi, sonunda bir dönüş türü belirtiminden ve lambda gövdesi. Daha fazla bilgi için [Lambda ifadesi söz dizimi](../cpp/lambda-expression-syntax.md). Bu örnek, PagedMem adlı bir segmentte bir lambda tanımlar:

```cpp
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };
```

Farklı segmentlere özel üye işlevleri, özellikle sanal üye işlevleri, yerleştirirken dikkatli olun. Bir temel sınıf yöntemi disk belleksiz bir segmente bulunduğunda, disk bellekli bir segmentte bulunan türetilmiş bir sınıfta sanal bir işlev tanımlarsanız, diğer temel sınıf yöntemleri veya kullanıcı kodu sanal yöntemin çağrılmasının bir sayfa hatasını tetikleyeceğini varsayabilir.

## <a name="example"></a>Örnek

Bu örnek gösterir nasıl bir **code_seg** özniteliği denetimleri segment yerleşimini örtük ve açık şablon uzmanlığı kullanıldığında:

```cpp
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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)