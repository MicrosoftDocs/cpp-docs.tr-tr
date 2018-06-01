---
title: Veritabanı destek dosyalarını yeniden dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- redistributing database support files
- database support files [C++], redistributing
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51697367480569e2d27a4cb67791f5fe4d39a8f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33323881"
---
# <a name="redistributing-database-support-files"></a>Veritabanı Destek Dosyalarını Yeniden Dağıtma
Veri erişim nesneleri (DAO) ve Microsoft Data Access SDK veritabanı teknolojileri için destek dosyalarını yeniden dağıtabilirsiniz.  
  
## <a name="installing-dao-support-files"></a>DAO destek dosyalarını yükleme  
 DAO en son sürümünü almak için bkz: [makale 239114: Microsoft Jet 4.0 veritabanı altyapısı için en son hizmet paketini edinmek nasıl](http://go.microsoft.com/fwlink/p/?linkid=198014) Microsoft Support Web sitesinde.  
  
## <a name="installing-microsoft-data-access-sdk-support-files"></a>Microsoft Data Access SDK destek dosyalarını yükleme  
 ODBC, OLE DB, ActiveX Data Objects (ADO) ve Uzak Veri Hizmetleri (RDS) için destek yüklemek amacıyla Mdac_typ.exe'yi kullanın. Mdac_typ.exe'yi bulunduğu... Visual Studio yükleme medyasında \WCU\MDAC28\ klasör. Ayrıca Mdac_typ.exe'yi dan indirebilirsiniz [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=198015) Web sitesi.  
  
 Daha fazla bilgi için üzerinde [MSDN](http://go.microsoft.com/fwlink/p/?linkid=198016) Web sitesi, "MDAC 2.8 SP1'i yeniden dağıtma" arayın. Uygulamanızı dağıtmak için Visual Studio Kurulum projelerini kullanıyorsanız bkz [dağıtım ve bağımlılıkları](http://msdn.microsoft.com/en-us/49e9b84d-bd6a-4388-b9ac-46ea79cf0733).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dosyalarını Yeniden Dağıtma](../ide/redistributing-visual-cpp-files.md)