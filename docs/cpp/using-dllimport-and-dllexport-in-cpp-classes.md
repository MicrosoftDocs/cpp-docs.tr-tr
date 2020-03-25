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
ms.openlocfilehash: 7d67660fa3b5d57c56d02d5526f0a9ea294a8eef
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187836"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ Sınıflarında dllimport ve dllexport Kullanma

**Microsoft 'a özgü**

Sınıfları **dllimport** veya C++ **dllexport** özniteliğiyle bildirebilirsiniz. Bu formlar, sınıfın tamamının içeri aktarılacağını veya verildiğini göstermez. Bu şekilde dışarı aktarılmış sınıflar, dışarı aktarılabilir sınıflar olarak adlandırılır.

Aşağıdaki örnek, verilebilir bir sınıfı tanımlar. Tüm üye işlevleri ve statik veriler verilir:

```cpp
#define DllExport   __declspec( dllexport )

class DllExport C {
   int i;
   virtual int func( void ) { return 1; }
};
```

Dışa aktarılabilir bir sınıfın üyeleri üzerinde **dllimport** ve **dllexport** özniteliklerinin açık kullanımına izin verilmez.

##  <a name="dllexport-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>dllexport sınıfları

Bir **dllexport**sınıfı bildirdiğinizde, tüm üye işlevleri ve statik veri üyeleri verilir. Aynı programda bu gibi tüm üyelerin tanımlarını sağlamanız gerekir. Aksi takdirde, bir bağlayıcı hatası oluşturulur. Bu kural için bir özel durum saf sanal işlevler için geçerlidir ve bu, açık tanımları sağlamanız gerekmez. Ancak, bir soyut sınıf için yıkıcının her zaman temel sınıfın yıkıcısı tarafından çağrıldığından, saf sanal Yıkıcılar her zaman bir tanım sağlamalıdır. Bu kuralların dışarı aktarılabilir sınıflar için aynı olduğunu unutmayın.

Sınıf türünün veya sınıfları döndüren işlevlerin verilerini dışa aktardığınızda, sınıfını dışarı aktardığınızdan emin olun.

##  <a name="dllimport-classes"></a><a name="_pluslang_dllexport_classesdllexportclasses"></a>dllimport sınıfları

Bir sınıf **dllimport**bildirdiğinizde, tüm üye işlevleri ve statik veri üyeleri içeri aktarılır. Sınıf olmayan türlerde **dllimport** ve **dllexport** davranışının aksine, statik veri üyeleri **dllimport** sınıfının tanımlandığı aynı programda bir tanımı belirtemez.

##  <a name="inheritance-and-exportable-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>Devralma ve dışarı aktarılabilir sınıflar

Dışarı aktarılabilir bir sınıfın tüm temel sınıfları dışarı aktarılabilir olmalıdır. Aksi takdirde, bir derleyici uyarısı oluşturulur. Ayrıca, aynı zamanda sınıflar olan tüm erişilebilir Üyeler dışarı aktarılabilir olmalıdır. Bu kural, bir **dllexport** sınıfının bir **dllimport** sınıfından devralmasını ve bir bir **dllexport** sınıfından devralacak bir **dllimport** sınıfından (ikincisi önerilmese de) izin verir. Kural olarak, DLL 'nin istemcisiyle erişilebilen her şey ( C++ erişim kurallarına göre), dışarı aktarılabilir arabirimin bir parçası olmalıdır. Bu, satır içi işlevlerde başvurulan özel veri üyelerini içerir.

##  <a name="selective-member-importexport"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>Seçmeli üye Içeri/dışarı aktarma

Bir sınıf içindeki üye işlevleri ve statik veriler örtük olarak dış bağlantıya sahip olduğundan, sınıfın tamamı verilemediği takdirde bunları **dllimport** veya **dllexport** özniteliğiyle bildirebilirsiniz. Sınıfın tamamı içeri veya içeri aktarılmışsa, üye işlevlerinin ve verilerin **dllimport** veya **dllexport** olarak açık bildirimi yasaktır. Bir sınıf tanımı içinde bir statik veri üyesini **dllexport**olarak bildirirseniz, bir tanım aynı program içinde (harici olmayan dış bağlantı ile olduğu gibi) bir yerde gerçekleşmelidir.

Benzer şekilde, **dllimport** veya **dllexport** öznitelikleriyle üye işlevleri de bildirebilirsiniz. Bu durumda, bir **dllexport** tanımını aynı programın içinde bir yerde sağlamanız gerekir.

Seçmeli üye içeri ve dışarı aktarma ile ilgili birkaç önemli noktayı aklınızda bulundurularak:

- Seçmeli üye içeri/dışarı aktarma en iyi şekilde, dışarı aktarılan sınıf arabiriminin daha kısıtlayıcı olan bir sürümünü sağlamak için kullanılır; diğer bir deyişle, dilden daha az ortak ve özel özellikler sunan bir DLL tasarlayabilmeniz için bir tane. Dışarı aktarılabilir arabirim için ince ayar yapmak için de kullanışlıdır. istemcinin, tanım olarak bazı özel verilere erişemediğini bildiğiniz durumlarda, tüm sınıfı dışarı aktarmanız gerekir.

- Bir sınıfta bir sanal işlevi dışa aktardığınızda, bunların tümünü dışarı aktarmanız gerekir ya da en azından istemcinin doğrudan kullanabileceği sürümleri sağlarsınız.

- Sanal işlevlerle seçmeli üye içeri/dışarı aktarma kullandığınız bir sınıfınız varsa, işlevlerin dışarı aktarılabilir arabirimde olması veya satır içi tanımlanmış olması (istemciye görünür) gerekir.

- Bir üyeyi **dllexport** olarak tanımlayabilir ancak sınıf tanımına eklemezseniz, bir derleyici hatası oluşturulur. Üyeyi sınıf üstbilgisinde tanımlamanız gerekir.

- Sınıf üyeleri için **dllimport** veya **dllexport** olarak tanımına izin verilse de, sınıf tanımında belirtilen arabirimi geçersiz kılamazsınız.

- Bir üye işlevini, bildirdiğiniz sınıf tanımının gövdesinden farklı bir yerde tanımlarsanız, işlev **dllexport** veya **dllimport** olarak tanımlanmışsa (Bu tanım, sınıf bildiriminde belirtilenden farklıysa) bir uyarı oluşturulur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
