---
title: Kısmi (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- partial_CPP
dev_langs:
- C++
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 92fd30b0b420080d33f9938bec4891ac80ac660d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597084"
---
# <a name="partial--c-component-extensions"></a>kısmi (C++ Bileşen Uzantıları)

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

*sınıf anahtarı*  
Bir sınıf ya da Windows çalışma zamanı tarafından desteklenen yapı bildiren bir anahtar sözcük. Her iki **başvuru sınıfı**, **değer sınıfının**, **ref struct**, veya **değeri yapı**.

*tanımlayıcı*  
Tanımlanan bir tür adı.

### <a name="remarks"></a>Açıklamalar

Kısmi bir sınıf bir dosya ve otomatik kod oluşturma yazılım bir sınıf tanımının bir parçası, değişiklik burada senaryolarını destekler; Örneğin, XAML Tasarımcısı — başka bir dosyaya aynı sınıftaki kod değiştirir. Kısmi bir sınıf kullanarak kodunuzu silmelerini otomatik kod oluşturucunun engelleyebilirsiniz. Visual Studio projesinde **kısmi** değiştiricisi için oluşturulan dosya otomatik olarak uygulanır.

İçerik: iki özel durum ile bir kısmi sınıf tanımı, tam sınıf tanımının içerebilen her şeyi içerebilir **kısmi** anahtar sözcüğü yoksayıldı. Ancak, sınıf erişilebilirlik belirtemezsiniz (örneğin, `public partial class X { ... };`), veya bir **declspec**.

Erişim tanımlayıcıları için bir parçalı sınıf tanımında kullanılan *tanımlayıcı* için bir sonraki kısmi veya tam sınıf tanımı içinde varsayılan erişilebilirlik etkilemez *tanımlayıcı*. Satır içi tanımları statik veri üyelerinin izin verilir.

Bildirim: Kısmi bir tanımını bir sınıfın *tanımlayıcı* yalnızca adı tanıtan *tanımlayıcı*, ancak *tanımlayıcı* bir sınıf gerektiren bir şekilde kullanılamaz tanımı. Adı *tanımlayıcısı* boyutunu bilmek kullanılamaz *tanımlayıcısı*, veya bir taban veya üye kullanılacak *tanımlayıcı* kadar tam tanımı derleyici karşılaştıktan sonra *tanımlayıcı*.

Sayı ve sıralama: sıfır veya daha fazla kısmi sınıf tanımları için olabilir *tanımlayıcı*. Her kısmi sınıf tanımını *tanımlayıcı* sözcüksel olarak bir tam tanımı gelmelidir *tanımlayıcı* (varsa tam tanımı için; Aksi takdirde, sınıf dışında kullanılamaz olarak İleri bildirimli) ancak iletme bildirimlerini önünde olmayan *tanımlayıcı*. Tüm sınıfı anahtarları aynı olmalıdır.

Tam tanımı: sınıfın tam tanımlarken *tanımlayıcı*, aynı durum geçerlidir gibi tanımını *tanımlayıcı* bildirilmiş tüm temel sınıflar, üyeler, vb. hangi sırayla Bunlar karşılaştı ve kısmi sınıflarında tanımlanan.

Şablonları: Şablon bir parçalı sınıf olamaz.

Genel türler: tam tanımı genel bir parçalı sınıf genel olabilir. Ancak her kısmi ve tam sınıf tam olarak biçimsel parametre adları da dahil olmak üzere aynı genel parametre olmalıdır.

Nasıl kullanılacağı hakkında daha fazla bilgi için **kısmi** anahtar sözcüğü, bkz: [kısmi sınıflar (C + +/ CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

(Bu dil özelliği ortak dil çalışma zamanı için geçerli değildir.)

## <a name="see-also"></a>Ayrıca Bkz.

[Kısmi sınıflar (C + +/ CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)