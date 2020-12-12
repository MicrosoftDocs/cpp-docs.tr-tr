---
description: 'Hakkında daha fazla bilgi edinin: code_seg (__declspec)'
title: code_seg (__declspec)
ms.date: 11/04/2016
f1_keywords:
- code_seg_cpp
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
ms.openlocfilehash: b382e0a758c28ffab297badda7670c1de3b08d32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171106"
---
# <a name="code_seg-__declspec"></a>code_seg (__declspec)

**Microsoft'a Özgü**

**Code_seg** bildirim özniteliği, işlev veya sınıf üyesi işlevleri için nesne kodunun depolanacağı. obj dosyasında bir çalıştırılabilir metin segmenti adlandırır.

## <a name="syntax"></a>Syntax

```
__declspec(code_seg("segname")) declarator
```

## <a name="remarks"></a>Açıklamalar

`__declspec(code_seg(...))`Özniteliği, kodun ayrı ayrı disk belleğine alınabilen veya bellekte kilitlenebileceği ayrı adlandırılmış kesimlere yerleştirilmesine izin vermez. Örneklenmiş şablonların ve derleyicinin ürettiği kodun yerleşimini denetlemek için bu özniteliği kullanabilirsiniz.

*Segment* , bir. obj dosyasındaki bir birim olarak belleğe yüklenen verilerin adlandırılmış bir bloğudur. *Metin segmenti* yürütülebilir kod içeren bir kesimdir. Terim *bölümü* genellikle kesimle birbirlerinin yerine kullanılır.

Tanımlandığında oluşturulan nesne kodu `declarator` `segname` , bir dar dize sabit değeri olan tarafından belirtilen metin segmentine konur. Adın `segname` bir bildirimde kullanılabilmesi için önce bir [section](../preprocessor/section.md) pragma içinde belirtilmesi gerekmez. Varsayılan olarak, hayır belirtildiğinde `code_seg` nesne kodu. Text adlı bir kesime konur. **Code_seg** öznitelik, mevcut [#pragma code_seg](../preprocessor/code-seg.md) yönergesini geçersiz kılar. Bir üye işlevine uygulanan **code_seg** özniteliği, kapsayan sınıfa uygulanan tüm **code_seg** özniteliğini geçersiz kılar.

Bir varlığın **code_seg** özniteliği varsa, aynı varlığa ait tüm bildirimler ve tanımlar aynı **code_seg** özniteliklerine sahip olmalıdır. Bir temel sınıfta **code_seg** özniteliği varsa, türetilen sınıfların aynı özniteliğe sahip olması gerekir.

Bir ad alanı kapsam işlevine veya bir üye işlevine **code_seg** özniteliği uygulandığında, bu işlevin nesne kodu belirtilen metin segmentine konur. Bu öznitelik bir sınıfa uygulandığında, sınıfın ve iç içe sınıfların tüm üye işlevleri, buna derleyici tarafından oluşturulan özel üye işlevleri de dahildir, belirtilen segmente yerleştirilir. Yerel olarak tanımlanan sınıflar — Örneğin, bir üye işlev gövdesinde tanımlanan sınıflar — kapsayan kapsamın **code_seg** özniteliğini almamayın.

Bir şablon sınıfı veya şablon işlevine bir **code_seg** özniteliği uygulandığında, şablonun tüm örtük uzmanlık alanı belirtilen kesime konur. Açık veya kısmi uzmanlık, **code_seg** özniteliğini birincil şablondan almıyor. Özelleştirmede aynı veya farklı bir **code_seg** özniteliği belirtebilirsiniz. Bir **code_seg** özniteliği açık şablon örneklemesine uygulanamaz.

Varsayılan olarak, derleyicinin ürettiği özel üye işlevi gibi bir kod bir .text segmente yerleştirilir. `#pragma code_seg`Yönerge bu varsayılanı geçersiz kılmaz. Derleyicinin ürettiği kodun nereye yerleştirileceğini denetlemek için sınıf, sınıf şablonu veya işlev şablonundaki **code_seg** özniteliğini kullanın.

Lambdalar, kapsayan kapsamından **code_seg** öznitelikleri devralınır. Lambda için bir segment belirtmek için, parametre bildirimi yan tümcesinden sonra ve herhangi bir kesilebilir veya özel durum belirtimi, tüm sondaki dönüş türü belirtimi ve lambda gövdesinden önce bir **code_seg** özniteliği uygulayın. Daha fazla bilgi için bkz. [lambda Ifadesi sözdizimi](../cpp/lambda-expression-syntax.md). Bu örnek, PagedMem adlı bir segmentte bir lambda tanımlar:

```cpp
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };
```

Farklı segmentlere özel üye işlevleri, özellikle sanal üye işlevleri, yerleştirirken dikkatli olun. Bir temel sınıf yöntemi disk belleksiz bir segmente bulunduğunda, disk bellekli bir segmentte bulunan türetilmiş bir sınıfta sanal bir işlev tanımlarsanız, diğer temel sınıf yöntemleri veya kullanıcı kodu sanal yöntemin çağrılmasının bir sayfa hatasını tetikleyeceğini varsayabilir.

## <a name="example"></a>Örnek

Bu örnek, örtük ve açık şablon özelleştirmesi kullanıldığında bir **code_seg** özniteliğinin segment yerleşimini nasıl denetlediğini gösterir:

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
