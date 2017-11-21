---
title: "Çerçeve (MFC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 09be7a5efbf3f78aa3cbc1862b811fff3d487c75
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="framework-mfc"></a>Framework (MFC)
Çalışmanızı Microsoft Foundation Class (MFC) kitaplığı framework ile büyük ölçüde birkaç önemli sınıfları ve birkaç Visual C++ Araçları dayanır. Bazı sınıfları Win32 uygulama programlama arabirimi (API) büyük bir kısmı kapsüller. Diğer sınıfları belgeler, görünümler ve uygulama gibi uygulama kavramlarını kapsüller. Hala başkalarının OLE özellikleri ve ODBC ve DAO veri erişimi işlevselliği kapsüller.  
  
 Örneğin, Win32'in kavramı penceresi, MFC sınıfı tarafından kapsüllenir `CWnd`. Diğer bir deyişle, C++ sınıfı adlı `CWnd` yalıtır ya da "sarmaladığı" `HWND` Windows penceresi temsil eden tanıtıcısı. Benzer şekilde, sınıf `CDialog` Win32 iletişim kutuları yalıtır.  
  
 Kapsülleme anlamına C++ sınıfı `CWnd`, örneğin, bir üye değişkeni türü içeren `HWND`, ve almayan Win32 işlevleri çağrıları sınıfının üye işlevleri kapsülleyen bir `HWND` bir parametre olarak. Sınıf üyesi işlevleri genellikle bunlar kapsülleyen Win32 işlevi aynı ada sahip.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [SDI ve MDI](../mfc/sdi-and-mdi.md)  
  
 [Belgeler, görünümler ve çerçeve](../mfc/documents-views-and-the-framework.md)  
  
 [Sihirbazlar ve kaynak düzenleyicileri](../mfc/wizards-and-the-resource-editors.md)  
  
## <a name="in-related-sections"></a>İçinde ilgili bölümler  
 [Framework'te derleme](../mfc/building-on-the-framework.md)  
  
 [Framework kodunuzu çağırması](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)  
  
 [Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)  
  
 [Pencere nesneleri](../mfc/window-objects.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows uygulamaları yazmak için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
