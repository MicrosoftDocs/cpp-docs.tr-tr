---
title: Framework (MFC)
ms.date: 11/04/2016
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
ms.openlocfilehash: ff29a867a8351a51ad7f09a5ca31d871fc67bab8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589312"
---
# <a name="framework-mfc"></a>Framework (MFC)

Microsoft Foundation Class (MFC) kitaplığı framework ile işinizi büyük ölçüde birkaç önemli sınıflarını ve çeşitli Visual C++ Araçları temel alır. Bazı sınıfları Win32 uygulama programlama arabirimi (API) büyük bir kısmı kapsüller. Diğer sınıfları, belgeler, görünümler ve uygulama gibi uygulama kavramlarını kapsüller. Yine de diğer OLE özellikleri ve ODBC ve DAO veri erişim işlevselliğini kapsüller.

MFC sınıfı tarafından Win32'ın kavramı penceresi, örneğin, kapsüllenir `CWnd`. Diğer bir deyişle, bir C++ sınıfı olarak adlandırılan `CWnd` kapsülleyen ya da "sarmaladığı" `HWND` Windows penceresini temsil eden bir işleyici. Benzer şekilde, sınıf `CDialog` Win32 iletişim kutuları kapsüller.

Kapsülleme anlamına C++ sınıfı `CWnd`, örneğin, bir üye değişkeni türü içeren `HWND`, ve bu çağrıları alan Win32 işlevlerine sınıfın üye işlevleri kapsülleyen bir `HWND` bir parametre olarak. Sınıf üyesi işlevleri, genellikle bunlar kapsülleyen Win32 işlevini aynı ada sahip.

## <a name="in-this-section"></a>Bu Bölümde

[SDI ve MDI](../mfc/sdi-and-mdi.md)

[Belgeler, Görünümler ve Çerçeve](../mfc/documents-views-and-the-framework.md)

[Sihirbazlar ve kaynak düzenleyicileri](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>İçinde ilgili bölümler

[Framework'te Derleme](../mfc/building-on-the-framework.md)

[Framework'ün Kodunuzu Çağırması](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)

[Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)

[İleti İşleme ve Eşleme](../mfc/message-handling-and-mapping.md)

[Pencere Nesneleri](../mfc/window-objects.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
