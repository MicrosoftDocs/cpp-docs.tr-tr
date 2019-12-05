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
ms.openlocfilehash: b42ba7c1a88a4de28eb3385bbf6cad068abf1944
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857235"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ Sınıflarında dllimport ve dllexport Kullanma

**Microsoft 'a özgü**

Sınıfları **dllimport** veya C++ **dllexport** özniteliğiyle bildirebilirsiniz. Bu formlar, sınıfının tamamının içe veya dışa aktarıldığını belirtir. Bu şekilde dışarı aktarılan sınıflar, dışarı aktarılabilir sınıflar olarak adlandırılır.

Aşağıdaki örnek dışarı aktarılabilen bir sınıfı tanımlar. Ait olan tüm üye işlevleri ve statik veriler dışarı aktarılır:

```cpp
#define DllExport   __declspec( dllexport )

class DllExport C {
   int i;
   virtual int func( void ) { return 1; }
};
```

Dışa aktarılabilir bir sınıfın üyeleri üzerinde **dllimport** ve **dllexport** özniteliklerinin açık kullanımına izin verilmez.

##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>dllexport sınıfları

Bir **dllexport**sınıfı bildirdiğinizde, tüm üye işlevleri ve statik veri üyeleri verilir. Bu tür üyelerin tümünü aynı programda tanımlamanız gerekir. Aksi halde bir bağlayıcı hatası meydana gelir. Bu kuralın tek istisnası, açık tanımlar sağlamak zorunda olmadığınız saf sanal işlevler için geçerlidir. Ancak özet sınıf için yok edici her zaman temel sınıf için yok edici tarafından çağrıldığından, saf sanal yok ediciler her zaman bir tanım sağlamalıdır. Bu kuralların dışa aktarılamayan sınıflar için de geçerli olduğunu unutmayın.

Sınıf türü verilerini veya sınıf döndüren işlevleri dışa aktarırken sınıfı aktardığınızdan emin olun.

##  <a name="_pluslang_dllexport_classesdllexportclasses"></a>dllimport sınıfları

Bir sınıf **dllimport**bildirdiğinizde, tüm üye işlevleri ve statik veri üyeleri içeri aktarılır. Sınıf olmayan türlerde **dllimport** ve **dllexport** davranışının aksine, statik veri üyeleri **dllimport** sınıfının tanımlandığı aynı programda bir tanımı belirtemez.

##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>Devralma ve dışarı aktarılabilir sınıflar

Dışa aktarılabilir bir sınıfın tüm temel sınıfları dışa aktarılabilir olmalıdır. Aksi halde bir derleyici uyarısı oluşturulur. Ayrıca, aynı zamanda sınıf olan tüm erişilebilir üyeler dışa aktarılabilir olmalıdır. Bu kural, bir **dllexport** sınıfının bir **dllimport** sınıfından devralmasını ve bir bir **dllexport** sınıfından devralacak bir **dllimport** sınıfından (ikincisi önerilmese de) izin verir. Bir kural olarak, DLL istemcisi için erişilebilir olan her şey (C++ erişim kurallarına göre), dışarı aktarılabilir arabirimin bir parçası olmalıdır. Bu, satır içi işlevlerde başvurulan özel veri üyelerini içerir.

##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>Seçmeli üye Içeri/dışarı aktarma

Bir sınıf içindeki üye işlevleri ve statik veriler örtük olarak dış bağlantıya sahip olduğundan, sınıfın tamamı verilemediği takdirde bunları **dllimport** veya **dllexport** özniteliğiyle bildirebilirsiniz. Sınıfın tamamı içeri veya içeri aktarılmışsa, üye işlevlerinin ve verilerin **dllimport** veya **dllexport** olarak açık bildirimi yasaktır. Bir sınıf tanımı içinde bir statik veri üyesini **dllexport**olarak bildirirseniz, bir tanım aynı program içinde (harici olmayan dış bağlantı ile olduğu gibi) bir yerde gerçekleşmelidir.

Benzer şekilde, **dllimport** veya **dllexport** öznitelikleriyle üye işlevleri de bildirebilirsiniz. Bu durumda, bir **dllexport** tanımını aynı programın içinde bir yerde sağlamanız gerekir.

Seçici üyelerin içe ve dışa aktarılması konusunda bazı önemli noktaların unutulmaması gerekir:

- Seçkin üye içe/dışa aktarma, daha kısıtlayıcı olan ve dışa aktarılan bir sınıf arabirimi için sürüm sağlamak için kullanılır; yani bu dilin izin vereceğinden daha az ortak ve özellik sunan bir DLL tasarlayabileceğiniz bir sürümdür. Dışa aktarılabilir arabirimde hassas ayarlamaları yapmak için de kullanışlıdır: tanımına göre istemcinin bazı özel verilere erişemediğini biliyorsanız sınıfın tamamını dışa aktarmanız gerekir.

- Bir sanal işlevi bir sınıfa dışa aktarırken tamamını dışa aktarmalı veya en azından istemcinin doğrudan kullanabileceği sürümleri sağlamalısınız.

- Seçici üye içe aktarma/dışa aktarma işlevlerini sanal işlevlerle kullandığınız bir sınıfınız varsa işlevlerin dışa aktarılabilir arabirimde olması veya satır içinde tanımlanmış olması (istemci tarafından görünür) gerekir.

- Bir üyeyi **dllexport** olarak tanımlayabilir ancak sınıf tanımına eklemezseniz, bir derleyici hatası oluşturulur. Sınıf üstbilgisinde üye tanımlamanız gerekir.

- Sınıf üyeleri için **dllimport** veya **dllexport** olarak tanımına izin verilse de, sınıf tanımında belirtilen arabirimi geçersiz kılamazsınız.

- Bir üye işlevini, bildirdiğiniz sınıf tanımının gövdesinden farklı bir yerde tanımlarsanız, işlev **dllexport** veya **dllimport** olarak tanımlanmışsa (Bu tanım, sınıf bildiriminde belirtilenden farklıysa) bir uyarı oluşturulur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)