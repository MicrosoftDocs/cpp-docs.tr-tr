---
title: partial (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- partial_CPP
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
ms.openlocfilehash: 0f9de5dda1b0838a624431e579e6bc6b328d9013
ms.sourcegitcommit: d77159732a8e782b2a1b7abea552065f2b6f61c1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2020
ms.locfileid: "93344702"
---
# <a name="partial--ccli-and-ccx"></a>partial (C++/CLI ve C++/CX)

**Partial** anahtar sözcüğü, aynı başvuru sınıfının farklı bölümlerinin bağımsız olarak ve farklı dosyalarda yazılmasını sağlar.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliği yalnızca Windows Çalışma Zamanı için geçerlidir.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

İki kısmi Tanım içeren bir başvuru sınıfı için, **kısmi** anahtar sözcük tanımın ilk oluşumuna uygulanır ve bu genellikle otomatik oluşturulan kodla yapılır ve böylece bir insan kodlayıcı anahtar sözcüğünü çok sık kullanamaz. Sınıfın sonraki tüm kısmi tanımları için, *sınıf anahtar* anahtar sözcüğünden ve sınıf tanımlayıcısından **kısmi** değiştiricisini atlayın. Derleyici önceden tanımlanmış bir başvuru sınıfı ve sınıf tanımlayıcısıyla karşılaştığında ancak **kısmi** anahtar sözcük tanımınızda, başvuru sınıfı tanımının tüm parçalarını tek bir tanım halinde dahili olarak birleştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
partial class-key identifier {
   /* The first part of the partial class definition.
      This is typically auto-generated */
}
// ...
class-key identifier {
   /* The subsequent part(s) of the class definition. The same
      identifier is specified, but the "partial" keyword is omitted. */
}
```

### <a name="parameters"></a>Parametreler

*sınıf anahtarı*<br/>
Windows Çalışma Zamanı tarafından desteklenen bir sınıf veya yapı bildiren bir anahtar sözcük. **Ref class** , **value class** , **ref struct** ya da **Value struct**.

*Tanımlayıcısını*<br/>
Tanımlı türün adı.

### <a name="remarks"></a>Açıklamalar

Kısmi bir sınıf, bir dosyada sınıf tanımının bir parçasını değiştirdiğiniz ve örneğin XAML Tasarımcısı gibi otomatik kod oluşturma yazılımlarının, başka bir dosyadaki aynı sınıftaki kodu değiştirdiği senaryoları destekler. Kısmi bir sınıf kullanarak otomatik kod oluşturucunun kodunuzun üzerine yazmasını engelleyebilirsiniz. Visual Studio projesinde, **kısmi** değiştirici oluşturulan dosyaya otomatik olarak uygulanır.

İçerik: iki özel durum Ile kısmi bir sınıf tanımı, **kısmi** anahtar sözcük atlandığında tam sınıf tanımının içerebileceği her şeyi içerebilir. Ancak, sınıf erişilebilirliği (örneğin, `public partial class X { ... };` ) veya bir **declspec** belirtemezsiniz.

*Tanımlayıcı* için kısmi sınıf tanımında kullanılan erişim belirticileri, *tanımlayıcı* için sonraki kısmi veya tam sınıf tanımında varsayılan erişilebilirliği etkilemez. Statik veri üyelerinin satır içi tanımlarına izin verilir.

Bildirim: bir sınıf *tanımlayıcısının* kısmi tanımı yalnızca ad *tanımlayıcısını* tanıtır, ancak *tanımlayıcı* bir sınıf tanımı gerektiren bir şekilde kullanılamaz. Ad *tanımlayıcısı* , *tanımlayıcı* boyutunu veya derleyicinin tam tanımıyla karşılaşana kadar bir taban veya *tanımlayıcı* üyesini kullanmak için *kullanılamaz.*

Sayı ve sıralama: *tanımlayıcı* için sıfır veya daha fazla kısmi sınıf tanımı olabilir. *Tanımlayıcının* her kısmi sınıf tanımı, *tanımlayıcının* bir tam tanımına (tam bir tanım varsa) ve bunun tersi durumda, bu sınıf, iletme bildirimleri hariç kullanılamaz, ancak *tanımlayıcı* bildirimlerinin önüne geçmemelidir. Tüm sınıf anahtarlarının eşleşmesi gerekir.

Tam tanım: sınıf *tanımlayıcısının* tam tanımı noktasında, bu davranış, *tanımlayıcı* tanımının tüm temel sınıfları, üyeleri, vb. ile karşılaştığı ve kısmi sınıflarda tanımlandığı sırada bildirmiş olması ile aynıdır.

Şablonlar: kısmi bir sınıf bir şablon olamaz.

Genel türler: tam tanım genel olması halinde kısmi bir sınıf genel olabilir. Ancak her kısmi ve tam sınıf, biçimsel parametre adları dahil olmak üzere tam olarak aynı genel parametrelere sahip olmalıdır.

**Kısmi** anahtar sözcüğü kullanma hakkında daha fazla bilgi için bkz. [kısmi sınıflar (C++/CX)](../cppcx/partial-classes-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliği ortak dil çalışma zamanı için geçerlidir.)

## <a name="see-also"></a>Ayrıca bkz.

[Kısmi sınıflar (C++/CX)](../cppcx/partial-classes-c-cx.md)
