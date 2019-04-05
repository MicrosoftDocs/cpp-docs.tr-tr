---
title: Kısmi (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- partial_CPP
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
ms.openlocfilehash: eb9b3907008147cb21f04aec5f42e4896fa35b3c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029952"
---
# <a name="partial--ccli-and-ccx"></a>Kısmi (C + +/ CLI ve C + +/ CX)

**Kısmi** farklı bölümlerini birbirinden bağımsız olarak ve farklı dosyalar yazılması gereken aynı başvuru sınıfı anahtar sözcüğü sağlar.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerlidir.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

İki kısmi tanım var olan bir başvuru sınıfı için **kısmi** anahtar sözcüğü tanımının ilk oluşum için geçerli olduğu ve bir insan Kodlayıcı anahtar sözcüğü çok sık kullanmaz, böylece bu genellikle otomatik olarak oluşturulan kodu tarafından yapılır. İçin tüm sonraki kısmi tanımlar sınıfın atlamak **kısmi** değiştiricisi gelen *sınıf anahtarı* anahtar sözcüğü ve sınıf tanımlayıcısı. Önceden tanımlanmış bir başvuru sınıfı ve sınıf tanımlayıcısı ancak Hayır derleyici karşılaştığında **kısmi** anahtar sözcüğü, dahili olarak tüm ref sınıf tanımında bir tanım bölümlerini birleştirir.

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
Bir sınıf ya da Windows çalışma zamanı tarafından desteklenen yapı bildiren bir anahtar sözcük. Her iki **başvuru sınıfı**, **değer sınıfının**, **ref struct**, veya **değeri yapı**.

*tanımlayıcı*<br/>
Tanımlanan bir tür adı.

### <a name="remarks"></a>Açıklamalar

Kısmi bir sınıf bir dosya ve otomatik kod oluşturma yazılım bir sınıf tanımının bir parçası, değişiklik burada senaryolarını destekler; Örneğin, XAML Tasarımcısı — başka bir dosyaya aynı sınıftaki kod değiştirir. Kısmi bir sınıf kullanarak kodunuzu silmelerini otomatik kod oluşturucunun engelleyebilirsiniz. Visual Studio projesinde **kısmi** değiştiricisi için oluşturulan dosya otomatik olarak uygulanır.

İçerik: İki özel durum ile tam sınıf tanımı varsa içerebilen her şeyi bir kısmi sınıf tanımını içeren **kısmi** anahtar sözcüğü yoksayıldı. Ancak, sınıf erişilebilirlik belirtemezsiniz (örneğin, `public partial class X { ... };`), veya bir **declspec**.

Erişim tanımlayıcıları için bir parçalı sınıf tanımında kullanılan *tanımlayıcı* için bir sonraki kısmi veya tam sınıf tanımı içinde varsayılan erişilebilirlik etkilemez *tanımlayıcı*. Satır içi tanımları statik veri üyelerinin izin verilir.

Bildirim: Kısmi bir sınıf tanımlaması *tanımlayıcı* yalnızca adı tanıtan *tanımlayıcı*, ancak *tanımlayıcı* bir sınıf tanımı gerektiren bir şekilde kullanılamaz. Adı *tanımlayıcısı* boyutunu bilmek kullanılamaz *tanımlayıcısı*, veya bir taban veya üye kullanılacak *tanımlayıcı* kadar tam tanımı derleyici karşılaştıktan sonra *tanımlayıcı*.

Sayı ve sıralama: Sıfır veya daha fazla kısmi sınıf tanımları için olabilir *tanımlayıcı*. Her kısmi sınıf tanımını *tanımlayıcı* sözcüksel olarak bir tam tanımı gelmelidir *tanımlayıcı* (varsa tam tanımı için; Aksi takdirde, sınıf dışında kullanılamaz olarak İleri bildirimli) ancak iletme bildirimlerini önünde olmayan *tanımlayıcı*. Tüm sınıfı anahtarları aynı olmalıdır.

Tam tanımı: Sınıfın tam tanımlarken *tanımlayıcı*, aynı durum geçerlidir gibi tanımını *tanımlayıcı* bildirilmiş tüm temel sınıflar, üyeler, vb. içinde oldukları sırayla karşılaştı ve kısmi sınıflar tanımlanmış.

Şablonları: Kısmi bir sınıf, bir şablon olamaz.

Genel türler: Kısmi bir sınıf tam tanımı genel bir genel olabilir. Ancak her kısmi ve tam sınıf tam olarak biçimsel parametre adları da dahil olmak üzere aynı genel parametre olmalıdır.

Nasıl kullanılacağı hakkında daha fazla bilgi için **kısmi** anahtar sözcüğü, bkz: [kısmi sınıflar (C + +/ CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliği ortak dil çalışma zamanı için geçerli değildir.)

## <a name="see-also"></a>Ayrıca bkz.

[Kısmi sınıflar (C + +/ CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)