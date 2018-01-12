---
title: "OLE DB sağlayıcı şablonları (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f95b32d62d964c83853025ed4e4af9b90e7a630a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-db-provider-templates-c"></a>OLE DB Sağlayıcı Şablonları (C++)
OLE DB, Microsoft evrensel veri erişimi stratejisi önemli bir parçasıdır. OLE DB tasarım, tüm veri kaynaklarından yüksek performanslı veri erişim sağlar. Hiç tablo verisi, bir veritabanından gelen bağımsız olarak OLE DB aracılığıyla görüntülenebilir. Esnekliği büyük miktarda güç sağlar.  
  
 İçinde anlatıldığı gibi [OLE DB Tüketicileri ve sağlayıcıları](../../data/oledb/ole-db-consumers-and-providers.md), OLE DB Tüketicileri ve sağlayıcıları kavramı kullanır. Tüketici veri isteğinde bulunur; Sağlayıcı veri tüketiciye tablo biçiminde döndürür. Programlama açısından bakıldığında, sağlayıcı tüketici yapabilirsiniz çağrısı uygulamalıdır olduğu Bu modelin en önemli çıkarımında bulunulur.  
  
## <a name="what-is-a-provider"></a>Bir sağlayıcı nedir?  
 OLE DB sağlayıcısı bir tüketici nesnesinden arabirimi çağrıları hizmet COM nesneleri tüketiciye (bir veri deposu olarak adlandırılır) dayanıklı bir kaynaktan bir tablo biçiminde veri aktarma kümesidir.  
  
 Sağlayıcıları, basit veya karmaşık olabilir. Sağlayıcı, daha fazla arabirim uygulayarak en az miktarda işlevselliği veya özelliği tam gelişmiş üretim kalitesi sağlayıcısıyla destekleyebilir. Bir sağlayıcı bir tablo döndürür, o tablosunun biçimini belirlemek için istemcinin izin ve bu verileri işlemleri.  
  
 COM nesneleri istemcisinden standart anlamı tüm OLE DB Tüketici dil (C++ gibi ve temel) bağımsız olarak herhangi bir sağlayıcıdan gelen veri erişebilmesini isteklerini işlemek için standart bir dizi her sağlayıcısını uygular.  
  
 Her COM nesnesi bazıları gereklidir ve bazıları isteğe bağlı olan birkaç arabirimleri içerir. Zorunlu arabirimleri uygulayarak, en düşük düzeyde herhangi bir istemci kullanabilmek için işlevsellik (uyumluluk denir) sağlayıcı güvence altına alır. Bir sağlayıcı ek işlevsellik sağlamak için isteğe bağlı arabirimler uygulayabilirsiniz. [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md) bu arabirimleri ayrıntılı açıklar. İstemci her zaman çağırmalıdır `QueryInterface` bir sağlayıcı belirli bir arabirim destekleyip desteklemediğini belirlemek için.  
  
## <a name="ole-db-specification-level-support"></a>OLE DB belirtim düzeyinde destek  
 OLE DB sağlayıcı şablonları OLE DB sürüm 2.7 belirtimini destekler. OLE DB sağlayıcı şablonları kullanarak, bir düzey 0 uyumlu sağlayıcı uygulayabilirsiniz. Sağlayıcı örneği Örneğin, dosya sistemini sorgulamak üzere DOS DIR komutunu yürütür non-MS-DOS komut sunucusunu uygulamak için şablonlar kullanır. Sağlayıcı örneği tablo veri döndürmek için standart OLE DB mekanizması bir satır kümesi dizin bilgilerini döndürür.  
  
 OLE DB Şablonları tarafından desteklenen en basit tür, komut içermeyen salt okunur bir sağlayıcıdır. Yer işareti ekleme ve okuma/yazma özelliği gibi komutları sağlayıcılarıyla de desteklenir. Ek kod yazarak okuma/yazma sağlayıcısı uygulayabilirsiniz. Dinamik satır kümeleri ve işlemler geçerli sürümü tarafından desteklenmez, ancak isterseniz bunları ekleyebilirsiniz.  
  
## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>Ne zaman bir OLE DB sağlayıcısı oluşturmanız gerekiyor mu?  
 Her zaman kendi sağlayıcınızı oluşturmanız gerekmez; Microsoft, birkaç paketlenmiş, standart sağlayıcıları sağlar **veri bağlantısı özelliklerini** Visual C++'ta iletişim kutusu. Evrensel veri erişimi stratejisi yararlanmak için bir OLE DB sağlayıcısı oluşturmak için ana nedeni olmasıdır. Bu nedenle bunun avantajlarından bazıları şunlardır:  
  
-   C++, Basic ve Visual Basic Scripting Edition gibi herhangi bir dil aracılığıyla verilere erişme. Kuruluşunuzdaki farklı programcıların aynı şekilde, bakılmaksızın aynı verilere erişmek için kullandıkları hangi dillerden sağlar.  
  
-   Verilerinizi diğer verilere gösterme, SQL Server, Excel ve erişim gibi kaynakları. Bu, farklı biçimleri arasında veri aktarmak istiyorsanız çok kullanışlı olabilir.  
  
-   Geçici veri kaynağı (heterojen) işlemlerine katılma. Bu veri depolama için çok etkili bir yol olabilir. OLE DB sağlayıcıları kullanarak verileri yerel biçiminde tutmak ve hala basit bir işlemle erişebilir.  
  
-   Verilerinize sorgu işleme gibi ek özellikler ekleme.  
  
-   Verilere nasıl yönetilebilir denetleyerek performansını artırma.  
  
-   Sağlamlık artırma. Özel veri biçimi varsa tek programcının erişebilir, risk altındadır. OLE DB Sağlayıcısı'nı kullanarak, programcıları için bu özel biçimi açabilirsiniz.  
  
## <a name="read-only-and-updatable-providers"></a>Salt okunur ve güncelleştirilebilir sağlayıcılar  
 Sağlayıcılar, karmaşıklık ve işlevsellik büyük ölçüde farklılık gösterebilir. Salt okunur sağlayıcılar ve güncelleştirilebilir sağlayıcılar sağlayıcıları sınıflandırmak yararlıdır:  
  
-   Visual C++ 6.0 yalnızca salt okunur sağlayıcılar desteklenmiyor. [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md) salt okunur sağlayıcıyı oluşturma açıklanır.  
  
-   Visual C++ güncelleştirebilirsiniz güncelleştirilebilir sağlayıcılar destekler (yazma) veri deposu. Güncelleştirilebilir sağlayıcılar hakkında daha fazla bilgi için bkz: [güncelleştirilebilir sağlayıcı oluşturma](../../data/oledb/creating-an-updatable-provider.md); [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek güncelleştirilebilir sağlayıcı örneğidir.  
  
 Daha fazla bilgi için bkz.:  
  
-   [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)  
  
-   [OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)  
  
-   [OLE DB Programlama](../../data/oledb/ole-db-programming.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri erişimi](../data-access-in-cpp.md)   
 [OLE DB SDK Belgeleri](https://msdn.microsoft.com/en-us/library/ms722784.aspx)   
 [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/en-us/library/ms713643.aspx)