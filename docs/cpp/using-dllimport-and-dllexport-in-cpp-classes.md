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
ms.openlocfilehash: 4687db45c767f4323c97aff0a685aa3aeeb83e94
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227016"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ Sınıflarında dllimport ve dllexport Kullanma

**Microsoft'a Özgü**

C++ sınıflarını **`dllimport`** veya **`dllexport`** özniteliğiyle bildirebilirsiniz. Bu formlar, sınıfın tamamının içeri aktarılacağını veya verildiğini göstermez. Bu şekilde dışarı aktarılmış sınıflar, dışarı aktarılabilir sınıflar olarak adlandırılır.

Aşağıdaki örnek, verilebilir bir sınıfı tanımlar. Tüm üye işlevleri ve statik veriler verilir:

```cpp
#define DllExport   __declspec( dllexport )

class DllExport C {
   int i;
   virtual int func( void ) { return 1; }
};
```

**`dllimport`** Ve **`dllexport`** özniteliklerinin verilebilir bir sınıfın üyeleri üzerinde açık olarak kullanılması yasaktır.

## <a name="dllexport-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a>dllexport sınıfları

Bir sınıf bildirdiğinizde **`dllexport`** , tüm üye işlevleri ve statik veri üyeleri verilir. Aynı programda bu gibi tüm üyelerin tanımlarını sağlamanız gerekir. Aksi takdirde, bir bağlayıcı hatası oluşturulur. Bu kural için bir özel durum saf sanal işlevler için geçerlidir ve bu, açık tanımları sağlamanız gerekmez. Ancak, bir soyut sınıf için yıkıcının her zaman temel sınıfın yıkıcısı tarafından çağrıldığından, saf sanal Yıkıcılar her zaman bir tanım sağlamalıdır. Bu kuralların dışarı aktarılabilir sınıflar için aynı olduğunu unutmayın.

Sınıf türünün veya sınıfları döndüren işlevlerin verilerini dışa aktardığınızda, sınıfını dışarı aktardığınızdan emin olun.

## <a name="dllimport-classes"></a><a name="_pluslang_dllexport_classesdllexportclasses"></a>dllimport sınıfları

Bir sınıf bildirdiğinizde **`dllimport`** , tüm üye işlevleri ve statik veri üyeleri içeri aktarılır. **`dllimport`** **`dllexport`** Sınıf olmayan türlerin ve üzerindeki davranışının aksine, statik veri üyeleri bir sınıfın tanımlandığı aynı programda bir tanımı belirtemez **`dllimport`** .

## <a name="inheritance-and-exportable-classes"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a>Devralma ve dışarı aktarılabilir sınıflar

Dışarı aktarılabilir bir sınıfın tüm temel sınıfları dışarı aktarılabilir olmalıdır. Aksi takdirde, bir derleyici uyarısı oluşturulur. Ayrıca, aynı zamanda sınıflar olan tüm erişilebilir Üyeler dışarı aktarılabilir olmalıdır. Bu kural, bir sınıfın bir sınıftan **`dllexport`** devralmasını **`dllimport`** ve sınıftan devralması için bir sınıftan **`dllimport`** **`dllexport`** (ikincisi önerilmese de) izin verir. Kural olarak, DLL 'nin istemcisiyle erişilebilen her şey (C++ erişim kurallarına göre), dışarı aktarılabilir arabirimin bir parçası olmalıdır. Bu, satır içi işlevlerde başvurulan özel veri üyelerini içerir.

## <a name="selective-member-importexport"></a><a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a>Seçmeli üye Içeri/dışarı aktarma

Bir sınıftaki üye işlevleri ve statik verilerin örtük olarak dış bağlantısı olduğundan, **`dllimport`** **`dllexport`** sınıfın tamamı verilemediği takdirde, veya özniteliğiyle bunları bildirebilirsiniz. Tüm sınıf içeri veya içeri aktarılmışsa, üye işlevleri ve verilerinin açık bildirimi **`dllimport`** veya olarak **`dllexport`** engellenir. Bir sınıf tanımı içinde bir statik veri üyesi bildirirseniz **`dllexport`** , bir tanım aynı program içinde (harici olmayan dış bağlantı ile olduğu gibi) bir yerde gerçekleşmelidir.

Benzer şekilde, veya öznitelikleri ile üye işlevleri bildirebilirsiniz **`dllimport`** **`dllexport`** . Bu durumda, **`dllexport`** aynı programda bir yerde bir tanım sağlamanız gerekir.

Seçmeli üye içeri ve dışarı aktarma ile ilgili birkaç önemli noktayı aklınızda bulundurularak:

- Seçmeli üye içeri/dışarı aktarma en iyi şekilde, dışarı aktarılan sınıf arabiriminin daha kısıtlayıcı olan bir sürümünü sağlamak için kullanılır; diğer bir deyişle, dilden daha az ortak ve özel özellikler sunan bir DLL tasarlayabilmeniz için bir tane. Dışarı aktarılabilir arabirim için ince ayar yapmak için de kullanışlıdır. istemcinin, tanım olarak bazı özel verilere erişemediğini bildiğiniz durumlarda, tüm sınıfı dışarı aktarmanız gerekir.

- Bir sınıfta bir sanal işlevi dışa aktardığınızda, bunların tümünü dışarı aktarmanız gerekir ya da en azından istemcinin doğrudan kullanabileceği sürümleri sağlarsınız.

- Sanal işlevlerle seçmeli üye içeri/dışarı aktarma kullandığınız bir sınıfınız varsa, işlevlerin dışarı aktarılabilir arabirimde olması veya satır içi tanımlanmış olması (istemciye görünür) gerekir.

- Bir üyeyi olarak tanımlayabilir **`dllexport`** ancak sınıf tanımına dahil değilseniz, bir derleyici hatası oluşturulur. Üyeyi sınıf üstbilgisinde tanımlamanız gerekir.

- Ya da olarak sınıf üyelerinin tanımına **`dllimport`** **`dllexport`** izin verilse de, sınıf tanımında belirtilen arabirimi geçersiz kılamazsınız.

- Bir üye işlevini, bildirdiğiniz sınıf tanımının gövdesinden farklı bir yerde tanımlarsanız, işlev **`dllexport`** veya **`dllimport`** (Bu tanım, sınıf bildiriminde belirtilenden farklıysa) bir uyarı oluşturulur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
