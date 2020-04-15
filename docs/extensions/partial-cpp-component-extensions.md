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
ms.openlocfilehash: 42e8cc9a20c96e65ed3ddf73d562fe014bd9fa28
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350005"
---
# <a name="partial--ccli-and-ccx"></a>partial (C++/CLI ve C++/CX)

**Kısmi** anahtar kelime, aynı ref sınıfının farklı bölümlerinin bağımsız olarak ve farklı dosyalarda yazılmasını sağlar.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliği yalnızca Windows Runtime için geçerlidir.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

İki kısmi tanımı olan bir ref sınıfı için **kısmi** anahtar kelime tanımın ilk oluşumuna uygulanır ve bu genellikle otomatik oluşturulan kod tarafından yapılır, böylece bir insan kodlayıcı anahtar sözcüğü çok sık kullanmaz. Sınıfın sonraki tüm kısmi tanımları için, **sınıf** *anahtar* sözcüğü nden ve sınıf tanımlayıcısından kısmi değiştiriciyi atla. Derleyici, daha önce tanımlanmış bir ref sınıfı ve sınıf tanımlayıcısı ile karşılaştığında ancak **kısmi** bir anahtar kelime olmadığında, ref sınıfı tanımının tüm bölümlerini tek bir tanımda dahili olarak birleştirir.

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
Windows Runtime tarafından desteklenen bir sınıf veya yapı bildiren bir anahtar kelime. Ya **ref sınıfı**, değer **sınıfı**, **ref struct**, ya da **değer struct**.

*Tanımlayıcı*<br/>
Tanımlanan türün adı.

### <a name="remarks"></a>Açıklamalar

Kısmi bir sınıf, sınıf tanımının bir bölümünü bir dosyada değiştirdiğiniz senaryoları destekler ve otomatik kod üreten yazılım (örneğin, XAML tasarımcısı- kodu başka bir dosyada aynı sınıfta değiştirir). Kısmi bir sınıf kullanarak, otomatik kod üretecisinin kodunuzu üzerine yazmasını engelleyebilirsiniz. Visual Studio projesinde, **kısmi** değiştirici otomatik olarak oluşturulan dosyaya uygulanır.

İçindekiler: İki özel durum dışında, kısmi sınıf tanımı, **kısmi** anahtar sözcük atlanırsa, tam sınıf tanımının içerebileceği her şeyi içerebilir. Ancak, sınıf erişilebilirliğini (örneğin,) `public partial class X { ... };`veya bir **declspec**belirtemezsiniz.

*Tanımlayıcı* için kısmi sınıf tanımında kullanılan erişim belirteçleri, tanımlayıcı *için*sonraki kısmi veya tam sınıf tanımındaki varsayılan erişilebilirliği etkilemez. Statik veri üyelerinin satır içinde tanımlarına izin verilir.

Bildirim: Sınıf tanımlayıcısının kısmi tanımı *yalnızca* ad *tanımlayıcısını*tanılar, ancak *tanımlayıcı* sınıf tanımı gerektiren bir şekilde kullanılamaz. Ad *tanımlayıcısı* *tanımlayıcının*boyutunu bilmek veya derleyici tanımlayıcının tam tanımıyla karşılaşAna *kadar* bir temel veya tanımlayıcı nın *üyesini*kullanmak için kullanılamaz.

Sayı ve sıralama: *Tanımlayıcı*için sıfır veya daha fazla kısmi sınıf tanımı olabilir. Tanımlayıcının her *identifier* kısmi sınıf tanımı sözlü olarak *tanımlayıcının* tam tanımından önce olmalıdır (tam bir tanım varsa; aksi takdirde, sınıf ileri beyan edildiği gibi kullanılamaz) ancak *tanımlayıcının*ileriye dönük bildirimlerinden önce olmamalıdır. Tüm sınıf anahtarları eşleşmelidir.

Tam tanım: Sınıf *tanımlayıcısının*tam tanımı noktasında, davranış, *tanımlayıcının* tanımının tüm taban sınıfları, üyeleri vb. kısmi sınıflarda karşılaşılan ve tanımlandıkları sırayla beyan ettiği gibi aynıdır.

Şablonlar: Kısmi bir sınıf şablon olamaz.

Genel: Tam tanım genel olabilirse kısmi bir sınıf genel olabilir. Ancak her kısmi ve tam sınıf, resmi parametre adları da dahil olmak üzere tam olarak aynı genel parametrelere sahip olmalıdır.

**Kısmi** anahtar kelimenin nasıl kullanılacağı hakkında daha fazla bilgi için kısmi [sınıflara (C++/CX)](https://go.microsoft.com/fwlink/p/?LinkId=249023)bakın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliği Ortak Dil Çalışma Zamanı için geçerli değildir.)

## <a name="see-also"></a>Ayrıca bkz.

[Kısmi Sınıflar (C++/CX)](https://go.microsoft.com/fwlink/p/?LinkId=249023)
