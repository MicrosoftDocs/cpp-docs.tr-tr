---
title: "ATL programı veya Denetim Kaynağı ve başlık dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a13a4c6ddb74a6f63b5da1171a3d4360199b508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL Programı veya Denetim Kaynağı ve Başlık Dosyaları
Oluşturduğunuz proje için belirttiğiniz seçeneklere bağlı olarak Visual Studio'da bir ATL projesi oluşturduğunuzda, aşağıdaki dosyaları oluşturulur.  
  
 Tüm bu dosyaları bulunan *Projname* dizin ve başlık dosyaları (.h dosyaları) klasör ya da Çözüm Gezgini kaynak dosyaları (.cpp) klasöründe.  
  
|Dosya adı|Açıklama|  
|---------------|-----------------|  
|*PROJNAME*.h|C++ arabirimi tanımlar ve GUID bildirimler ATLSample.idl içinde tanımlanan öğeleri içeren ana içerme dosyası. Derleme sırasında MIDL tarafından yeniden oluşturur.|  
|*PROJNAME*.cpp|Ana program kaynak dosyası. DLL dışarı aktarmaları bir işlem sunucusu için uygulanması ve uygulanmasının içeren `WinMain` yerel bir sunucu için. Bir hizmet için bu ayrıca tüm hizmet yönetim işlevlerini uygular.|  
|Kaynak.h|Kaynak dosya için üstbilgi dosyası.|  
|StdAfx.cpp|StdAfx.h ve Atlimpl.cpp dosyaları içerir.|  
|StdAfx.h|ATL üstbilgi dosyaları içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC programı veya Denetim Kaynağı ve başlık dosyaları](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR projeleri](../ide/files-created-for-clr-projects.md)