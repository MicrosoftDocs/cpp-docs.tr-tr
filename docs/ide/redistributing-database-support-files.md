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
ms.openlocfilehash: 55888388158cbe005709cbe8a4989071213b5c77
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195734"
---
# <a name="redistributing-database-support-files"></a>Veritabanı Destek Dosyalarını Yeniden Dağıtma
Veri erişim nesneleri (DAO) için ve Microsoft Data Access SDK'SİNDEKİ veritabanı teknolojileri için destek dosyalarını yeniden dağıtabilirsiniz.  
  
## <a name="installing-dao-support-files"></a>DAO destek dosyalarını yükleme  
 DAO'nun en son sürümünü edinmek için bkz: [makale 239114: Microsoft Jet 4.0 Veritabanı Altyapısı'nın en son hizmet paketini almalarına nasıl](http://go.microsoft.com/fwlink/p/?linkid=198014) Microsoft Support Web sitesi.  
  
## <a name="installing-microsoft-data-access-sdk-support-files"></a>Microsoft Data Access SDK destek dosyalarını yükleme  
 ODBC, OLE DB, ActiveX Data Objects (ADO) ve Uzak Veri Hizmetleri (RDS) için destek yüklemek amacıyla Mdac_typ.exe'yi kullanın. Mdac_typ.exe bulunan... Visual Studio yükleme medyasında \WCU\MDAC28\ klasör. Mdac_typ.exe nden de indirebilirsiniz [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=198015) Web sitesi.  
  
 Daha fazla bilgi için üzerinde [MSDN](http://go.microsoft.com/fwlink/p/?linkid=198016) Web sitesi, "MDAC 2.8 SP1 yeniden dağıtma" arayın. Uygulamanızı dağıtmak için Visual Studio Kurulum projelerini kullanıyorsanız bkz [dağıtım ve bağımlılıkları](https://msdn.microsoft.com/49e9b84d-bd6a-4388-b9ac-46ea79cf0733).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dosyalarını Yeniden Dağıtma](../ide/redistributing-visual-cpp-files.md)