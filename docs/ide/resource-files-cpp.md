---
title: "Kaynak dosyaları (C++) | Microsoft Docs"
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
- resource files
- resources [C++]
- file types [C++], resource files
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 097ae6d1486292d7dcc62dd4191e16f57e6f0a3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-files-c"></a>Kaynak Dosyalar (C++)
Kullanıcıya bilgi sağlamak arabirim öğeleri kaynaklardır. Bit eşlemler, simgeler, araç çubukları ve İmleçler tüm kaynaklardır. Bazı kaynaklar menüden seçerek veya iletişim kutusunda veri girme gibi bir eylem gerçekleştirmek üzere kullanılabilirler.  
  
 Bkz: [kaynaklarla çalışmak](../windows/working-with-resource-files.md) daha fazla bilgi için.  
  
|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|  
|---------------|------------------------|--------------------------------|-----------------|  
|*PROJNAME*.rc|*PROJNAME*|Kaynak dosyaları|Kaynak betik dosyasını projesi için. Kaynak betik dosyasını proje ve proje için (örneğin, araç çubukları, iletişim kutularını veya HTML) seçilen destek türüne bağlı olarak aşağıdakileri içerir:<br /><br /> -Varsayılan menü tanımı.<br />-Hızlandırıcı ve dize tabloları.<br />-Varsayılan **hakkında** iletişim kutusu.<br />-Başka bir iletişim kutusu.<br />-Simge dosyası (res\\*Projname*.ico).<br />-Sürüm bilgisi.<br />-Bit eşlemler.<br />-Araç.<br />-HTML dosyaları.<br /><br /> Kaynak dosyanın standart Microsoft Foundation Class kaynakları dosyası Afxres.rc içerir.|  
|Kaynak.h|*PROJNAME*|Üstbilgi Dosyaları|Proje tarafından kullanılan kaynakları için tanımları içeren kaynak üstbilgi dosyası.|  
|*PROJNAME*.rc2|*PROJNAME*\res|Kaynak dosyaları|Projesi tarafından kullanılan ek kaynakları içeren komut dosyası. Projenin .rc dosyasını üstündeki .rc2 dosya içerebilir.<br /><br /> Bir .rc2 dosyası birkaç farklı proje tarafından kullanılan kaynakları dahil etmek için kullanışlıdır. Birkaç kez farklı projeleri için aynı kaynakları oluşturmak yerine bir .rc2 dosyaya yerleştirin ve ana .rc dosyasına .rc2 dosyası içerir.|  
|*PROJNAME*.def|*PROJNAME*|Kaynak dosyaları|DLL projesi modül tanım dosyası. Bir denetim için ad ve açıklama denetiminin yanı sıra, çalışma zamanı öbek boyutunu sağlar.|  
|*PROJNAME*.ico|*PROJNAME*\res|Kaynak Dosyalar|Proje veya denetim için simge dosyası. Uygulamanın en aza bu simgesi görünür. Ayrıca uygulama içinde kullanılan **hakkında** kutusu. Varsayılan olarak, MFC MFC simgesi sağlar ve ATL ATL simgesi sağlar.|  
|*PROJNAME*Doc.ico|*PROJNAME*\res|Kaynak Dosyalar|Belge/görünüm mimarisi desteği içeren bir MFC projesine simge dosyası.|  
|ToolBar.bmp|*PROJNAME*\res|Kaynak Dosyalar|Uygulama veya araç ya da palet denetim temsil eden bit eşlem dosyası. Bu bit eşlemi projenin kaynak dosyasında dahil edilir. İçinde ilk araç çubuğu ve durum çubuğu yapılandırılan **CMainFrame** sınıfı.|  
|Ribbon.mfcribbon ms|*PROJNAME*\res|Kaynak Dosyalar|Şeritte düğmeleri, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren kaynak dosyası. Daha fazla bilgi için bkz: [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)