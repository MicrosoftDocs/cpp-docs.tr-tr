---
title: OLE DB programlamaya genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Universal Data Access
- OLE DB, about OLE DB
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5fea82dfd7d3f9cdd64d0eab66e44ac1a486abac
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49989898"
---
# <a name="ole-db-programming-overview"></a>OLE DB Programlamaya Genel Bakış

OLE DB yüksek performanslı, COM tabanlı veritabanı teknolojisidir. Verileri, depolandığı biçiminde bağımsız erişmek için ortak bir yol sunar. Tipik iş durumunda, çok büyük miktarda bilgi Kurumsal veritabanlarında depolanmaz. Bu bilgiler (örneğin, FAT veya NTFS), dosya sisteminde dizinli sıralı dosyaları, kişisel veritabanları (örneğin, erişimi), elektronik tablolar (Excel gibi) proje planlama uygulamaları (örneğin, Proje) ve e-posta (örneğin, Outlook) bulunur. OLE DB, bir OLE DB Sağlayıcı veri deposunda sahip olduğu sürece, aynı şekilde, herhangi bir türden veri deposuna erişim sağlar.
  
OLE DB, bunlar DBMS veya ister çeşitli veri kaynaklarına erişen uygulamalar geliştirmenize olanak sağlar. OLE DB, sağlanan veri kaynağı için uygun DBMS işlevselliğini destekleyen COM arabirimleri kullanarak evrensel erişim mümkün kılar. COM gereksiz çoğaltma hizmetlerinin azaltır ve yalnızca veri kaynakları arasında aynı zamanda diğer uygulamalar arasında birlikte çalışabilirlik ekranı.  
  
## <a name="benefits-of-com"></a>COM avantajları  

Bu, COM burada devreye girer. OLE DB, COM arabirimleri kümesidir. Veri kümesi arabirimleri erişerek bir veritabanı bileşenler Matrisine matris düzenleyebilirsiniz.  
  
COM belirtimine göre OLE DB katan ve tutarlı, yeniden kullanılabilir bölümlerini DBMS işlevi kapsülleyen arabirimleri genişletilebilir ve sürdürülebilir bir koleksiyonunu tanımlar. Bu arabirimler satır kapsayıcıları, sorgu işlemci ve çok çeşitli bilgi kaynakları işlem Tekdüzen erişim sağlayan işlem düzenleyicileri gibi DBMS bileşenleri sınırlarını tanımlayın.  
 
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Şablonları](../../data/oledb/ole-db-templates.md)