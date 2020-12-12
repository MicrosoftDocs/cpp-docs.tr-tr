---
description: 'Daha fazla bilgi edinin: OLE DB sağlayıcı şablonları (C++)'
title: OLE DB Sağlayıcı Şablonları (C++)
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
ms.openlocfilehash: 8706fcd9467e6d184633917d7c83ac81ad137b9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286923"
---
# <a name="ole-db-provider-templates-c"></a>OLE DB Sağlayıcı Şablonları (C++)

OLE DB, Microsoft Evrensel veri erişim stratejisinin önemli bir parçasıdır. OLE DB tasarımı, herhangi bir veri kaynağından yüksek performanslı veri erişimine izin verir. Tablo verileri, bir veritabanından gelmiş olup olmamasına bakılmaksızın OLE DB aracılığıyla görüntülenebilir. Esneklik size inanılmaz bir güç sağlar.

[OLE DB tüketicileri ve sağlayıcılar](../../data/oledb/ole-db-consumers-and-providers.md)bölümünde açıklandığı gibi, ole db tüketiciler ve sağlayıcılar kavramını kullanır. Tüketici veri istekleri yapar; sağlayıcı, verileri bir tablo biçiminde tüketiciye döndürür. Bir programlama perspektifinden, bu modelin en önemli bir engel, sağlayıcının tüketicinin yapamayacağı herhangi bir çağrıyı uygulaması gerekir.

## <a name="what-is-a-provider"></a>Sağlayıcı nedir?

OLE DB sağlayıcı, bir tüketici nesnesinden arabirim çağrılarına sunan bir COM nesneleri kümesidir ve verileri, dayanıklı bir kaynaktan (veri deposu olarak adlandırılır) bir tablosal biçimde, tüketiciye aktararak.

Sağlayıcılar basit veya karmaşık olabilir. Sağlayıcı, daha fazla arabirim uygulayarak en az miktarda işlevselliği veya tam bir blown üretim kalitesi sağlayıcısını destekleyebilir. Sağlayıcı bir tablo döndürebilir, istemcinin bu tablonun biçimini belirlemesine ve bu veriler üzerinde işlemler gerçekleştirmesine izin verebilir.

Her sağlayıcı, istemciden gelen istekleri işlemek için standart bir COM nesneleri kümesi uygular, standart bir OLE DB tüketicisinin dile bakılmaksızın (C++ ve temel) herhangi bir sağlayıcıdan veriye erişebileceği standart anlamına gelir.

Her bir COM nesnesi, bazıları gerekli ve bazıları isteğe bağlı olan çeşitli arabirimler içerir. Zorunlu arabirimleri uygulayarak bir sağlayıcı, istemcilerin kullanabilmesi gereken en düşük işlevsellik düzeyini (uyumluluk olarak adlandırılır) garanti eder. Sağlayıcı, ek işlevsellik sağlamak için isteğe bağlı arabirimler uygulayabilir. [OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md) bu arabirimleri ayrıntılı olarak açıklar. `QueryInterface`Bir sağlayıcının belirli bir arabirimi destekleyip desteklemediğini öğrenmek için istemci her zaman çağırmalıdır.

## <a name="ole-db-specification-level-support"></a>OLE DB belirtim düzeyi desteği

OLE DB sağlayıcısı şablonları OLE DB sürüm 2,7 belirtimini destekler. OLE DB sağlayıcı şablonlarını kullanarak, düzey 0 ile uyumlu bir sağlayıcı uygulayabilirsiniz. Örnek, `Provider` Örneğin, dosya sistemini sorgulamak IÇIN DOS DIR komutunu yürüten SQL olmayan bir komut sunucusunu uygulamak için şablonları kullanır. `Provider`Örnek, tablo verilerini döndürmek için standart OLE DB mekanizması olan bir satır kümesindeki dizin bilgilerini döndürür.

OLE DB Şablonları tarafından desteklenen en basit sağlayıcı türü, komut içermeyen bir salt okuma sağlayıcıdır. Komutları içeren sağlayıcılar, bookişaretleme ve okuma/yazma özellikleri gibi de desteklenir. Ek kod yazarak bir okuma/yazma sağlayıcısı uygulayabilirsiniz. Dinamik satır kümeleri ve işlemler geçerli sürüm tarafından desteklenmez, ancak isterseniz bunları ekleyebilirsiniz.

## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>OLE DB sağlayıcısı oluşturmanız ne zaman gerekir?

Her zaman kendi sağlayıcınızı oluşturmanız gerekmez; Microsoft, Visual C++ **veri bağlantısı özellikleri** iletişim kutusunda çok sayıda önceden paketlenmiş standart sağlayıcı sağlar. OLE DB sağlayıcısı oluşturmanın temel nedeni, evrensel veri erişim stratejisinden faydalanabilir. Bunun avantajlarından bazıları şunlardır:

- C++, temel ve Visual Basic Scripting Edition gibi herhangi bir dilde verilere erişme. Kuruluşunuzdaki farklı programcıların, kullandıkları dilde bağımsız olarak aynı veriye aynı verilere erişmesini sağlar.

- Verilerinizi SQL Server, Excel ve erişim gibi diğer veri kaynaklarına açın. Bu, farklı biçimler arasında veri aktarmak istiyorsanız yararlı olabilir.

- Veriler arası kaynak (heterojen) işlemlerine katılım. Bu, veri depolamaya yönelik etkili bir yol olabilir. OLE DB sağlayıcıları kullanarak, verileri yerel biçiminde tutabilir ve yine de basit bir işlemde bu verilere erişebilirsiniz.

- Verilerinize sorgu işleme gibi ek özellikler ekleme.

- Nasıl işleneceğini denetleyerek verilere erişmenin performansını artırma.

- Artan sağlamlık. Yalnızca bir programcının erişebileceği özel bir veri biçimine sahipseniz risk altında olursunuz. OLE DB sağlayıcıları kullanarak, bu özel biçimi tüm Programcılarınız için açabilirsiniz.

## <a name="read-only-and-updatable-providers"></a>Read-Only ve güncelleştirilebilir sağlayıcılar

Sağlayıcılar karmaşıklık ve işlevsellikten büyük ölçüde farklılık gösterebilir. Sağlayıcıları salt okuma sağlayıcıları ve güncelleştirilebilir sağlayıcılar olarak kategorilere ayırmak yararlı olur:

- Visual C++ 6,0 desteklenen yalnızca salt okunurdur sağlayıcılar. [OLE DB sağlayıcı](../../data/oledb/creating-an-ole-db-provider.md) oluşturmak, salt okunurdur bir sağlayıcının nasıl oluşturulduğunu açıklar.
- Visual C++, veri deposunu güncelleştirebilen (yazabilmesi) güncelleştirilebilir sağlayıcıları destekler. Güncelleştirilebilir sağlayıcılar hakkında daha fazla bilgi için bkz. [güncelleştirilebilir bir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md); [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneği, güncelleştirilebilir sağlayıcıya bir örnektir.

Daha fazla bilgi için bkz:

- [OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)

- [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)

- [OLE DB Programlama](../../data/oledb/ole-db-programming.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Erişimi](../data-access-in-cpp.md)<br/>
[SDK belgelerini OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[OLE DB Programcı başvurusu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)<br/>
