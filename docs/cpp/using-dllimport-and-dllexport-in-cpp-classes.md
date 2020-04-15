---
title: C++ Sınıflarında dllimport ve dllexport Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- exporting classes [C++]
- declarations [C++], class
- exportable classes [C++]
- classes [C++], declaring
- classes [C++], exportable and inheritance
- inheritance [C++], exportable classes [C++]
- dllimport attribute [C++], classes
- declaring classes [C++]
- dllexport attribute [C++]
- dllexport attribute [C++], classes [C++]
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
ms.openlocfilehash: c0a2c96a37f58c956976980beafd5ecbed4d1318
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365112"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ Sınıflarında dllimport ve dllexport Kullanma

**Microsoft'a Özgü**

C++ sınıflarını **dllimport** veya **dllexport** özniteliği ile bildirebilirsiniz. Bu formlar, sınıfın tamamının içe aktarıldığını veya dışa aktarıldığını ima eder. Bu şekilde dışa aktarılan sınıflara dışa aktarılabilir sınıflar denir.

Aşağıdaki örnek, dışa aktarılabilir bir sınıf tanımlar. Tüm üye işlevleri ve statik verileri dışa aktarılır:

```cpp
#define DllExport   __declspec( dllexport )

class DllExport C {
   int i;
   virtual int func( void ) { return 1; }
};
```

Dışa aktarılabilir sınıfın üyeleri üzerinde **dllimport** ve **dllexport** özniteliklerinin açık kullanımının yasak olduğunu unutmayın.

## <a name="dllexport-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>dllexport Sınıfları

Bir sınıf **dllexport**olarak beyan ettiğinizde, tüm üye işlevleri ve statik veri üyeleri dışa aktarılır. Tüm bu üyelerin tanımlarını aynı programda sağlamanız gerekir. Aksi takdirde, bir bağlayıcı hatası oluşturulur. Bu kuralın tek istisnası, açık tanımlar sağlamanız gerekmeyen saf sanal işlevler için geçerlidir. Ancak, soyut bir sınıf için bir yıkıcı her zaman taban sınıf için yıkıcı tarafından çağrıldığı için, saf sanal yıkıcılar her zaman bir tanım sağlamalıdır. Bu kuralların dışa aktarılmaz sınıflar için aynı olduğunu unutmayın.

Sınıf türü veya sınıf döndüren işlevler verilerini dışa aktarAcaksanız, sınıfı dışa aktardığınızdan emin olun.

## <a name="dllimport-classes"></a><a name="_pluslang_dllexport_classesdllexportclasses"></a>dllimport Sınıflar

Bir sınıf **dllimport**olarak beyan ettiğinizde, tüm üye işlevleri ve statik veri üyeleri alınır. Dllimport ve **dllexport'un** sınıf dışı türlerdeki davranışından farklı olarak, statik veri üyeleri aynı programda **dllimport** **dllimport** sınıfının tanımlandığı bir tanım belirtemez.

## <a name="inheritance-and-exportable-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>Kalıtım ve Dışa Aktarılabilir Sınıflar

Dışa aktarılabilir sınıfın tüm taban sınıfları dışa aktarılabilir olmalıdır. Değilse, derleyici uyarısı oluşturulur. Ayrıca, aynı zamanda sınıfları olan tüm erişilebilir üyeler dışa aktarılabilir olmalıdır. Bu kural, **dllexport** sınıfının **dllimport** sınıfından, **dllimport** sınıfının da **dllexport** sınıfından devralmasına izin verir (ikincisi önerilmese de). Kural olarak, DLL istemcisi için erişilebilir olan her şey (C++ erişim kurallarına göre) dışa aktarılabilir arabirimin bir parçası olmalıdır. Bu, satır satır işlevlerinde başvurulan özel veri üyelerini içerir.

## <a name="selective-member-importexport"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>Seçici Üye İthalat/İhracat

Bir sınıf içindeki üye işlevler ve statik verilerin örtülü olarak dış bağlantısı olduğundan, sınıfın tamamı dışa aktarılamadığı sürece bunları **dllimport** veya **dllexport** özniteliği ile bildirebilirsiniz. Sınıfın tamamı içe aktarılır veya dışa aktarılırsa, üye işlevlerin ve verilerin **dllimport** veya **dllexport** olarak açık beyanı yasaktır. Bir statik veri üyesini sınıf tanımı içinde **dllexport**olarak bildirirseniz, aynı program içinde bir yerde bir tanım olmalıdır (sınıf dışı dış bağlantıda olduğu gibi).

Benzer şekilde, **dllimport** veya **dllexport** öznitelikleri ile üye işlevleri bildirebilirsiniz. Bu durumda, aynı program içinde bir yerde bir **dllexport** tanımı sağlamanız gerekir.

Seçici üye ithalat ve ihracatı ile ilgili birkaç önemli noktaya dikkat etmek faydalıdır:

- Seçici üye alma/dışa aktarma en iyi dışa aktarılan sınıf arabiriminin daha kısıtlayıcı bir sürümünü sağlamak için kullanılır; diğer bir tanesi, dilin izin vereceğinden daha az genel ve özel özelliği ortaya çıkaran bir DLL tasarlayabilirsiniz. Ayrıca, dışa aktarılabilir arabirimi hassas ayarlamak için de yararlıdır: istemcinin, tanım gereği, bazı özel verilere erişemediğini bildiğinizde, tüm sınıfı dışa aktarmanız gerekmez.

- Bir sınıfta bir sanal işlev dışa aktarın, bunların tümünün dışa aktarMası veya en azından istemcinin doğrudan kullanabileceği sürümleri sağlamanız gerekir.

- Sanal işlevlere sahip seçici üye alma/dışa aktarma kullandığınız bir sınıfa sahipseniz, işlevlerin dışa aktarılabilir arabirimde veya tanımlı satır içinde (istemci tarafından görülebilir) olması gerekir.

- Bir üyeyi **dllexport** olarak tanımlar, ancak sınıf tanımına eklemezseniz, derleyici hatası oluşturulur. Üyeyi sınıf üstbilgisinde tanımlamanız gerekir.

- Sınıf üyelerinin **dllimport** veya **dllexport** olarak tanımlanmasına izin verilse de, sınıf tanımında belirtilen arabirimi geçersiz kılamazsınız.

- Bir üye işlevi, ilân ettiğiniz sınıf tanımının gövdesi dışında bir yerde tanımlarsanız, işlev **dllexport** veya **dllimport** olarak tanımlanırsa (bu tanım sınıf bildiriminde belirtilenden farklıysa) bir uyarı oluşturulur.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
