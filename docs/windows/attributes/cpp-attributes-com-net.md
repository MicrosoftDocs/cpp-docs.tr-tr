---
title: COM ve .NET için C++ öznitelikleri
ms.custom: index-page
ms.date: 11/19/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI], reference topics
ms.assetid: 613a3611-b3eb-4347-aa38-99b654600e1c
ms.openlocfilehash: 734d82a30df3e143a6f47cb1b3eca2cd778830bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214935"
---
# <a name="c-attributes-for-com-and-net"></a>COM ve .NET için C++ öznitelikleri

Microsoft, COM programlama ve C++ .NET Framework ortak dil çalışma zamanı geliştirmeyi kolaylaştıran bir öznitelikler kümesi tanımlar. Kaynak dosyalarınıza öznitelikler eklediğinizde, derleyici kod eklemek veya oluşturulan nesne dosyalarındaki kodu değiştirmek için sağlayıcı dll 'Leriyle birlikte çalışarak. Bu öznitelikler. IDL dosyaları, arabirimler, tür kitaplıkları ve diğer COM öğeleri oluşturulmasına yardımcı olur. Tümleşik geliştirme ortamında (IDE), öznitelikleri sihirbazlar ve Özellikler penceresi tarafından desteklenir.

Öznitelikler, COM nesneleri yazmak için gereken bazı ayrıntılı kodları ortadan kaldırlarken, en iyi şekilde kullanabilmek için [com temel](/windows/win32/com/the-component-object-model) esaları 'nda bir arka plana ihtiyacınız vardır.

> [!NOTE]
> C++ Standart öznitelikler arıyorsanız, bkz. [öznitelikler](../../cpp/attributes.md).

## <a name="purpose-of-attributes"></a>Özniteliklerin Amacı

Özellikler, C++ dilin klasik yapısını bozmadan, şu anda mümkün olmayan yönlere genişletilir. Öznitelikler, sağlayıcıların (ayrı dll 'Ler) dil işlevselliğini dinamik olarak genişlemesine olanak tanır. Özniteliklerin birincil amacı, bileşen geliştiricisinin üretkenlik düzeyini artırmanın yanı sıra COM bileşenlerinin yazılmasını basitleştirmektir. Öznitelikler, sınıflar, veri üyeleri veya C++ üye işlevleri gibi neredeyse her bir yapı için uygulanabilir. Aşağıda, bu yeni teknolojinin sağladığı avantajlardan bir vurgulaması verilmiştir:

- Tanıdık ve basit bir çağırma kuralı sunar.

- , Makroların aksine hata ayıklayıcı tarafından tanınan ekli kodu kullanır.

- Temel sınıflardan, hiçbir uygulama ayrıntısı olmadan kolayca türetmeye olanak tanır.

- Bir COM bileşeni için gereken büyük miktarda IDL kodunu birkaç kısa özniteliğe koyar.

Örneğin, genel ATL sınıfına basit bir olay havuzu uygulamak için, [event_receiver](event-receiver.md) özniteliğini `CMyReceiver`gibi belirli bir sınıfa uygulayabilirsiniz. `event_receiver` özniteliği daha sonra, uygun kodu nesne dosyasına C++ ekleyen Microsoft derleyicisi tarafından derlenir.

```cpp
[event_receiver(com)]
class CMyReceiver
{
   void handler1(int i) { ... }
   void handler2(int i, float j) { ... }
}
```

Daha sonra, [event_source](event-source.md)kullanarak oluşturabileceğiniz bir olay kaynağından olayları işlemek (iç işlev [__hook](../../cpp/hook.md)kullanarak) `CMyReceiver` Yöntemler `handler1` ve `handler2` ayarlayabilirsiniz.

## <a name="basic-mechanics-of-attributes"></a>Özniteliklerin Temel Mekanikleri

Projenize öznitelik eklemenin üç yolu vardır. İlk olarak, bunları kaynak kodunuza el ile ekleyebilirsiniz. İkinci olarak, projenize bir nesnenin özellik kılavuzunu kullanarak bunları ekleyebilirsiniz. Son olarak, çeşitli sihirbazları kullanarak bunları ekleyebilirsiniz. **Özellikler** penceresini ve çeşitli sihirbazları kullanma hakkında daha fazla bilgi için bkz. [Visual Studio projeleri- C++ ](../../build/creating-and-managing-visual-cpp-projects.md).

Daha önce olduğu gibi, Proje yapılandırıldığında, derleyici her C++ kaynak dosyayı ayrıştırır ve bir nesne dosyası üretir. Ancak, derleyici bir öznitelik ile karşılaştığında ayrıştırılır ve sözdizimsel olarak doğrulanır. Derleyici daha sonra kod eklemek veya derleme zamanında başka değişiklikler yapmak için bir öznitelik sağlayıcısını dinamik olarak çağırır. Sağlayıcının uygulanması, öznitelik türüne göre farklılık gösterir. Örneğin, ATL ile ilgili öznitelikler Atlprov. dll tarafından uygulanır.

Aşağıdaki şekilde, derleyici ve öznitelik sağlayıcısı arasındaki ilişki gösterilmektedir.

![Bileşen özniteliği iletişimi](../media/vccompattrcomm.gif "Bileşen özniteliği iletişimi")

> [!NOTE]
> Öznitelik kullanımı, kaynak dosyanın içeriğini değiştirmez. Oluşturulan öznitelik kodunun tek zaman hata ayıklama oturumları sırasında görünür. Ayrıca, projedeki her kaynak dosya için öznitelik değiştirme sonuçlarını görüntüleyen bir metin dosyası oluşturabilirsiniz. Bu yordam hakkında daha fazla bilgi için bkz. [/FX (eklenen kodu Birleştir)](../../build/reference/fx-merge-injected-code.md) ve [eklenen kodu hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

Çoğu C++ yapı gibi özniteliklerin, uygun kullanımını tanımlayan bir özellikler kümesi vardır. Bu, özniteliğin bağlamı olarak adlandırılır ve öznitelik bağlam tablosunda her öznitelik başvurusu konusu için belirtilir. Örneğin, [coclass](coclass.md) özniteliği yalnızca var olan bir sınıfa veya yapıya, C++ kaynak dosya içinde herhangi bir yere eklenebilen [cpp_quote](cpp-quote.md) özniteliği aksine uygulanabilir.

## <a name="building-an-attributed-program"></a>Öznitelikli Program Oluşturma

Kaynak kodunuza görsel C++ öznitelikler koyduktan sonra, Microsoft C++ derleyicisinin sizin için bir tür kitaplığı ve. IDL dosyası oluşturmasını isteyebilirsiniz. Aşağıdaki bağlayıcı seçenekleri. tlb ve. IDL dosyalarını oluşturmanıza yardımcı olur:

- [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)

- [/IGNOREıDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/MıDL](../../build/reference/midl-specify-midl-command-line-options.md)

- [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)

Bazı projeler birden çok bağımsız. IDL dosyası içerir. Bunlar iki veya daha fazla. tlb dosyası üretmek ve isteğe bağlı olarak onları kaynak bloğuna bağlamak için kullanılır. Bu senaryo, Visual C++'te Şu anda desteklenmiyor.

Ayrıca görsel C++ BAĞLAYıCı, IDL ile ilgili tüm öznitelik bilgilerini tek BIR MIDL dosyasına çıktı. Tek bir projeden iki tür kitaplığı oluşturmanın bir yolu olmayacaktır.

## <a name="attribute-contexts"></a><a name="contexts"></a>Öznitelik bağlamları

C++öznitelikler dört temel alan kullanılarak açıklanabilir: (**Için geçerlidir**), tekrarlanabilir veya yoksa (**yinelenebilir**), diğer özniteliklerin gerekli varlığı (**gerekli öznitelikler**) ve diğer özniteliklerle uyumsuzluklar (**geçersiz öznitelikler**). Bu alanlar, her bir özniteliğin başvuru konusunun birlikte bulunan bir tabloda listelenir. Bu alanların her biri aşağıda açıklanmıştır.

### <a name="applies-to"></a>Uygulanan Öğe

Bu alan, belirtilen öznitelik C++ için geçerli hedef olan farklı dil öğelerini açıklar. Örneğin, bir öznitelik, **Uygulanacağı** alanında "sınıf" belirtiyorsa, bu özniteliğin yalnızca geçerli C++ bir sınıfa uygulanabileceğini gösterir. Özniteliği bir sınıfın üye işlevine uygulanırsa, bir sözdizimi hatası oluşur.

Daha fazla bilgi için bkz. [kullanıma göre öznitelikler](attributes-by-usage.md).

### <a name="repeatable"></a>Tekrarlanabilir

Bu alan, özniteliğin yinelenen olarak aynı hedefe uygulanıp uygulanamayacağını belirtir. Özniteliklerin çoğunluğu tekrarlanabilir değildir.

### <a name="required-attributes"></a>Gerekli öznitelikler

Bu alan, belirtilen özniteliğin düzgün şekilde çalışması için mevcut olması gereken (yani aynı hedefe uygulanan) diğer öznitelikleri listeler. Bir özniteliğin Bu alan için herhangi bir girişe sahip olması yaygın bir durumdur.

### <a name="invalid-attributes"></a>Geçersiz öznitelikler

Bu alan, belirtilen öznitelikle uyumsuz olan diğer öznitelikleri listeler. Bir özniteliğin Bu alan için herhangi bir girişe sahip olması yaygın bir durumdur.

## <a name="in-this-section"></a>Bu Bölümde

[Öznitelik Programlama SSS](attribute-programming-faq.md)<br/>
[Gruplara Göre Öznitelikler](attributes-by-group.md)<br/>
[Kullanıma Göre Öznitelikler](attributes-by-usage.md)<br/>
[Öznitelikler Alfabetik Başvurusu](attributes-alphabetical-reference.md)
