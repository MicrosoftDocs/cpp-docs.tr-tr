---
title: "CDataConnection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
dev_langs: C++
helpviewer_keywords: CDataConnection class
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e7ce953304792e5c04c406025a656c22eb8eee13
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnection-class"></a>CDataConnection Sınıfı
Veri kaynağı ile bağlantı yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDataConnection  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|Oluşturucu. Oluşturur ve başlatır bir `CDataConnection` nesnesi.|  
|[Kopyalama](../../data/oledb/cdataconnection-copy.md)|Varolan bir veri bağlantısı bir kopyasını oluşturur.|  
|[Açık](../../data/oledb/cdataconnection-open.md)|Başlatma dizesi kullanarak bir veri kaynağı için bir bağlantı açar.|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|Geçerli bağlantı üzerinde yeni bir oturum açar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[BOOL işleci](../../data/oledb/cdataconnection-operator-bool.md)|Geçerli oturumu açık olup olmadığını belirler.|  
|[işleç bool değeri](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|Geçerli oturumu açık olup olmadığını belirler.|  
|[işleç CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|Kapsanan bir başvuru döndürür `CDataSource` nesnesi.|  
|[CDataSource * işleci](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|İşaretçi içerdiği için döndüren `CDataSource` nesnesi.|  
|[işleç CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)|Kapsanan bir başvuru döndürür `CSession` nesnesi.|  
|[işleç CSession *](../../data/oledb/cdataconnection-operator-csession-star.md)|İşaretçi içerdiği için döndüren `CSession` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDataConnection`gerekli nesneleri (veri kaynağı ve oturum) ve bir veri kaynağına bağlanırken gerçekleştirmeniz gereken iş bazıları yalıtır çünkü istemciler oluşturmak için yararlı bir sınıf  
  
 Olmadan `CDataConnection`, oluşturmak zorunda bir `CDataSource` nesne, çağrı kendi [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) yöntemi, bir örneğini oluşturmak bir [CSession](../../data/oledb/csession-class.md) nesne, çağrı kendi [ Açık](../../data/oledb/csession-open.md) yöntemi, ardından oluşturun bir [CCommand](../../data/oledb/ccommand-class.md) nesne ve çağrı kendi **açık*** yöntemleri.  
  
 İle `CDataConnection`, yalnızca bir bağlantı nesnesi oluşturmak, bir başlatma dizesi geçirin ve ardından komutları açmak için bu bağlantıyı kullanmak gerekir. Veritabanı bağlantınızı sürekli olarak kullanmayı planlıyorsanız, bu bağlantıyı açık tutmak için iyi bir fikirdir ve `CDataConnection` Bunu yapmak için kullanışlı bir yol sağlar.  
  
> [!NOTE]
>  Birden çok oturumu işlemek için gereken bir veritabanı uygulaması oluşturuyorsanız kullanmanız gerekecektir [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)