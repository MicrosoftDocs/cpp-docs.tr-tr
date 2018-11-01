---
title: OLE DB Sağlayıcı Şablonları (C++)
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
ms.openlocfilehash: 99bf377ff10a2978a912666e787ed3a024d8654e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485199"
---
# <a name="ole-db-provider-templates-c"></a>OLE DB Sağlayıcı Şablonları (C++)

OLE DB, Microsoft evrensel veri erişimi stratejisinin önemli bir parçasıdır. OLE DB tasarım herhangi bir veri kaynağından yüksek performanslı veri erişimi sağlar. Hiç tablo verisi, bir veritabanından gelen bağımsız olarak OLE DB aracılığıyla görüntülenebilir. Esneklik, İnanılmaz derecede güç sağlar.

İçinde anlatıldığı gibi [OLE DB Tüketicileri ve sağlayıcıları](../../data/oledb/ole-db-consumers-and-providers.md), OLE DB Tüketicileri ve sağlayıcıları kavramını kullanır. Tüketici veri istekleri yapar; Sağlayıcı, tüketiciye verileri tablo biçiminde döndürür. Programlama açısından bakıldığında, bu modelin en önemli olduğu çıkarımında sağlayıcı tüketici yapabilirsiniz tüm çağrıların uygulamalıdır olur.

## <a name="what-is-a-provider"></a>Sağlayıcısı nedir?

Bir OLE DB sağlayıcısı bir tüketici nesnesinden arabirimi çağrıları hizmet COM nesneleri verileri bir tablosal biçimde (bir veri deposu olarak adlandırılır), dayanıklı bir kaynaktan tüketiciye aktarma kümesidir.

Sağlayıcıları, basit veya karmaşık olabilir. Sağlayıcı işlevselliği ya da tam gelişmiş üretim kalitesinde sağlayıcısına en az miktarda daha fazla arabirim uygulayarak destekler. Sağlayıcı bir tablo döndürür, bu tabloyu biçimini belirlemek için istemcinin izin ve bu veri işlemleri.

Standart bir standart anlama sahip istemci dil (C++ gibi ve temel) bağımsız olarak herhangi bir sağlayıcıdan gelen tüm OLE DB Tüketici veri erişebilirsiniz istekleri işlemek için COM nesnelerinin her bir sağlayıcı uygular.

Her bir COM nesnesi bazıları gereklidir ve bazıları isteğe bağlı olan birkaç arabirimleri içerir. Zorunlu arabirimleri uygulayan bir sağlayıcı, herhangi bir istemci kullanabilir (uyumluluk denir) işlevselliği asgari düzeyde garanti eder. Bir sağlayıcı ek işlevsellik sağlamak için isteğe bağlı arabirimler uygulayabilirsiniz. [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md) ayrıntılı Bu arabirimler açıklanmaktadır. İstemci her zaman çağırmalıdır `QueryInterface` bir sağlayıcının belirli bir arabirim destekleyip desteklemediğini belirlemek için.

## <a name="ole-db-specification-level-support"></a>OLE DB belirtim düzeyinde destek

OLE DB sağlayıcı şablonları, OLE DB sürüm 2.7 belirtimini destekler. OLE DB sağlayıcı şablonları kullanarak, bir düzey 0 uyumlu sağlayıcısı uygulayabilirsiniz. `Provider` Örnek, örneğin, şablonları dosya sistemini sorgulamaya DOS DIR komutunu yürüten bir non-MS-DOS komut sunucusunu uygulamak için kullanır. `Provider` Örnek tablo veri döndürmek için standart OLE DB mekanizması bir satır kümesi dizin bilgileri döndürür.

OLE DB Şablonları tarafından desteklenen en basit türü ile hiçbir komut salt okunur bir sağlayıcıdır. Yer işareti ekleme ve okuma/yazma özellikleri gibi komutları sağlayıcılarıyla de desteklenir. Okuma/yazma sağlayıcısı, ek kod yazarak uygulayabilirsiniz. Dinamik satır kümeleri ve işlem geçerli sürümü tarafından desteklenmiyor, ancak isterseniz bunları ekleyebilirsiniz.

## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>OLE DB sağlayıcısı oluşturmak ne zaman ihtiyacınız var?

Her zaman kendi sağlayıcısı oluşturmanız gerekmez; Microsoft, birkaç önceden paketlenmiş, standart sağlayıcı sağlar **veri bağlantı özellikleri** Visual C++'ta iletişim kutusu. Evrensel veri erişimi stratejisi yararlanmak için bir OLE DB sağlayıcısı oluşturmak için temel nedeni olan. Bu nedenle bunun avantajlarından bazıları şunlardır:

- C++, Basic ve Visual Basic Scripting Edition gibi herhangi bir dilde aracılığıyla verilere erişme. Kuruluşunuzdaki farklı programcılar aynı şekilde, bakılmaksızın aynı verilere erişmek için kullandıkları hangi dillerden sağlar.

- Verilerinizi SQL Server, Excel ve erişim gibi diğer veri kaynaklarına açın. Bu, farklı biçimler arasında veri aktarmak istiyorsanız yararlı olabilir.

- Çapraz-veri kaynağı (heterojen) işlemlerine katılma. Bu, veri ambarlama için etkili bir yol olabilir. OLE DB sağlayıcıları kullanarak, verileri kendi yerel biçiminde tutmak ve yine de basit bir işlemle erişebilir.

- Verilerinizi sorgu işleme gibi ek özellikler ekliyor.

- Değişiklikleri denetleyerek veri erişimi performans artırma.

- Sağlamlık artırma. Özel veri biçimi varsa tek programcının erişebilir, risk altındadır. OLE DB Sağlayıcısı'nı kullanarak bu özel biçimi, programcılar için açabilirsiniz.

## <a name="read-only-and-updatable-providers"></a>Salt okunur ve güncelleştirilebilir sağlayıcılar

Sağlayıcıları, karmaşıklığı ve işlevselliği önemli ölçüde farklılık gösterebilir. Sağlayıcıları salt okunur sağlayıcılar ve güncelleştirilebilir sağlayıcılar kategorilere ayırma kullanışlıdır:

- Visual C++ 6.0 yalnızca salt okunur sağlayıcılar desteklenmiyor. [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md) salt okunur sağlayıcıyı oluşturma anlatılmaktadır.
- Visual C++ güncelleştirebilirsiniz güncelleştirilebilir sağlayıcılar destekler (yazma) veri deposu. Güncelleştirilebilir sağlayıcılar hakkında daha fazla bilgi için bkz: [güncelleştirilebilir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md); [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örnek güncelleştirilebilir sağlayıcı örneği verilmiştir.

Daha fazla bilgi için bkz.:

- [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)

- [OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)

- [OLE DB Programlama](../../data/oledb/ole-db-programming.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Veri Erişimi](../data-access-in-cpp.md)<br/>
[OLE DB SDK Belgeleri](/previous-versions/windows/desktop/ms722784)<br/>
[OLE DB Programcının Başvurusu](/previous-versions/windows/desktop/ms713643)<br/>
