---
title: COM ve .NET için C++ öznitelikleri | Microsoft Docs
ms.custom: index-page
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
ms.assetid: 613a3611-b3eb-4347-aa38-99b654600e1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 66188f1879c42eaf9429675a2f235130e263211f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072531"
---
# <a name="c-attributes-for-com-and-net"></a>COM ve .NET için C++ öznitelikleri

Microsoft, COM programlama ve .NET Framework ortak dil çalışma zamanı geliştirme basitleştiren C++ öznitelikleri kümesi tanımlar. Öznitelikler, kaynak dosyaları eklediğinizde, derleyici sağlayıcısı kod ekleyin veya oluşturulan nesne dosyaları kodu değiştirmek için DLL'ler ile çalışır. Bu öznitelikler .idl dosyaları, arabirimler, tür kitaplıklarını ve diğer COM öğeleri oluşturmaya yardımcı. Tümleşik geliştirme ortamında (IDE), öznitelikler ve Özellikler penceresinde sihirbazlar tarafından desteklenir.

Öznitelikleri COM nesneleri yazmak için gerekli ayrıntılı kodlama bazılarını ortadan kaldırır, ancak arka planda ihtiyacınız [COM Temelleri](/windows/desktop/com/the-component-object-model) en iyi şekilde kullanmak için.

> [!NOTE]
> C++ standart özniteliklerini arıyorsanız bkz [öznitelikleri](../../cpp/attributes.md).

## <a name="purpose-of-attributes"></a>Özniteliklerin Amacı

Öznitelikleri, C++ dil Klasik yapısını bozmadan şu anda mümkün yönde genişletin. Öznitelikleri sağlayıcıları (dinamik olarak dil işlevlerini genişletmek için ayrı DLL'ler) sağlar. Öznitelikleri birincil amacı, bileşen Geliştirici üretkenliği düzeyini artırmak ek olarak, COM bileşenleri geliştirme kolaylaştırmaktır. Öznitelikleri uygulanabilir sınıfları, veri üyeleri veya üye işlevleri gibi neredeyse tüm C++ yapı için. Bu yeni teknoloji tarafından sağlanan avantajların bir Vurgu verilmiştir:

- Tanıdık ve basit bir çağırma kuralı kullanıma sunar.

- Kullanır, makroları, hata ayıklayıcı tarafından tanınan kod eklenir.

- Kolay qname'den türetme sıkıcı uygulama ayrıntılarını olmadan temel sınıflar sağlar.

- IDL kod gerekli birkaç kısa özniteliklere sahip bir COM bileşeni tarafından büyük miktarda değiştirir.

Örneğin, bir basit olay havuzu için genel bir ATL sınıf uygulamak için uygulayabilirsiniz [event_receiver](event-receiver.md) gibi belirli bir sınıfa öznitelik `CMyReceiver`. `event_receiver` Özniteliği uygun kod nesnesi dosyasına ekler için Visual C++ derleyicisi tarafından derlenen sonra.

```cpp
[event_receiver(com)]
class CMyReceiver
{
   void handler1(int i) { ... }
   void handler2(int i, float j) { ... }
}
```

Ardından ayarlayabilirsiniz `CMyReceiver` yöntemleri `handler1` ve `handler2` olayları işlemek için (iç işlevi kullanarak [__hook](../../cpp/hook.md)) kullanarak oluşturabileceğiniz bir olay kaynağından [event_source](event-source.md).

## <a name="basic-mechanics-of-attributes"></a>Özniteliklerin Temel Mekanikleri

Öznitelikleri projenize eklemek için üç yolu vardır. İlk olarak, bunları el ile kaynak kodunuza ekleyebilirsiniz. İkinci olarak, projenizde bir nesnenin özellik kılavuzu kullanarak bunları ekleyebilirsiniz. Son olarak, bunları çeşitli sihirbazlar kullanarak ekleyebilirsiniz. Kullanma hakkında daha fazla bilgi için **özellikleri** penceresi ve çeşitli sihirbazlar [oluşturma ve yönetme, Visual C++ projeleri](../../ide/creating-and-managing-visual-cpp-projects.md).

Proje derlenirken olarak önce derleyici bir nesne dosyası üretmek her C++ kaynak dosyası ayrıştırır. Ancak, derleyici bir öznitelik karşılaştığında, ayrıştırılır ve sözdizimsel olarak doğrulandı. Derleyici daha sonra kod ekleyin veya derleme zamanında başka değişiklikler yapmak için bir öznitelik sağlayıcısı dinamik olarak çağırır. Sağlayıcının uygulama özniteliği türüne bağlı olarak farklılık gösterir. Örneğin, ATL ilgili öznitelikleri Atlprov.dll tarafından uygulanır.

Aşağıdaki şekil, derleyici ve öznitelik sağlayıcısı arasındaki ilişki gösterilmektedir.

![Bileşen özniteliği iletişimini](../media/vccompattrcomm.gif "vcCompAttrComm")

> [!NOTE]
> Öznitelik kullanımı, kaynak dosyasının içeriğini değiştirmez. Kodu oluşturulan özniteliği görünür olup yalnızca bir kez, hata ayıklama oturumları sırasında dir. Ayrıca, projedeki her kaynak dosyası için öznitelik değiştirme sonuçlarını görüntüleyen bir metin dosyası oluşturabilirsiniz. Bu yordamı hakkında daha fazla bilgi için bkz. [/Fx (eklenen kodu Birleştir)](../../build/reference/fx-merge-injected-code.md) ve [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

Çoğu C++ yapılarına uygun kullanımlarını tanımlayan bir dizi özellikleri özniteliklere sahiptir. Bu öznitelik bağlamı olarak adlandırılır ve öznitelik bağlamı tablosunda her öznitelik başvuru konusu ele. Örneğin, [coclass'ı](coclass.md) özniteliği yalnızca uygulanabilir bir varolan bir sınıf veya yapı, başlangıcı yerine sonundan [cpp_quote](cpp-quote.md) C++ kaynak dosyası içinde istenen yere eklenebileceğini özniteliği.

## <a name="building-an-attributed-program"></a>Öznitelikli Program Derleme

Kaynak kodunuza Visual C++ öznitelikleri geçirdikten sonra sizin için bir tür kitaplığı ve .idl dosyası oluşturmak için Visual C++ derleyicisi isteyebilirsiniz. Aşağıdaki bağlayıcı Yardım .tlb ve .idl dosyalarını derleme seçenekleri:

- [/ IDLOUT](../../build/reference/idlout-name-midl-output-files.md)

- [/ IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/ MIDL](../../build/reference/midl-specify-midl-command-line-options.md)

- [/ TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)

Bazı projeler, birden çok bağımsız .idl dosyaları içerir. Bunlar, iki veya daha fazla .tlb dosyaları oluşturur ve isteğe bağlı olarak bunları kaynak bloğu içine bağlamak için kullanılır. Bu senaryo, Visual C++'da şu anda desteklenmiyor.

Ayrıca, Visual C++ bağlayıcı tüm öznitelik IDL ile ilgili bilgileri tek bir MIDL dosyasına çıkarır. İki tür kitaplıklarının tek bir projeden oluşturmak olanaksız olacaktır.

## <a name="contexts"></a> Öznitelik bağlamları

C++ öznitelikleri, dört temel alan kullanarak tanımlanabilen: Bunlar uygulanabilir hedef (**uygulanacağı**), tekrarlanabilir olsalar da (**Repeatable**), diğer öznitelikleri (varlığınıgerekli **Gerekli öznitelik**) ve diğer özniteliklerini uyumsuzluklar (**geçersiz öznitelikler**). Bu alanlar, her özniteliğin başvuru konusu eşlik eden bir tabloda listelenir. Bu alanların her biri aşağıda açıklanmıştır.

### <a name="applies-to"></a>Uygulandığı öğe:

Bu alan, belirtilen öznitelik için yasal hedefleri olan farklı C++ dil öğeleri açıklar. Örneğin, "class" bir öznitelik belirtir, **uygulanacağı** alan, bu gösterir öznitelik yalnızca geçerli bir C++ sınıfı için uygulanabilir. Öznitelik bir sınıfın bir üye işlevine uygulandığında sözdizimi hatası neden olur.

Daha fazla bilgi için [kullanıma göre öznitelikler](attributes-by-usage.md).

### <a name="repeatable"></a>Tekrarlanabilir

Bu alan özniteliği aynı hedefe art arda uygulanabilir olup olmadığını belirtir. Özniteliklerin çoğu tekrarlanabilir değildir.

### <a name="required-attributes"></a>Gerekli öznitelikleri

Bu alan olması gereken diğer özniteliklerini listeler (yani aynı hedefe) düzgün çalışması belirtilen öznitelik varsa. Bu alan herhangi bir giriş bir öznitelik için seyrek.

### <a name="invalid-attributes"></a>Geçersiz öznitelikler

Bu alan, belirtilen bir öznitelik ile uyumsuz olan diğer öznitelikleri listeler. Bu alan herhangi bir giriş bir öznitelik için seyrek.

## <a name="in-this-section"></a>Bu Bölümde

[Öznitelik Programlama SSS](attribute-programming-faq.md)<br/>
[Gruplara Göre Öznitelikler](attributes-by-group.md)<br/>
[Kullanıma Göre Öznitelikler](attributes-by-usage.md)<br/>
[Öznitelikler Alfabetik Başvurusu](attributes-alphabetical-reference.md)