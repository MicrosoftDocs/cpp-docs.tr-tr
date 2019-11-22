---
title: Framework (MFC)
ms.date: 09/17/2019
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
ms.openlocfilehash: 387f53e3123b6863fcf218da39c7c5e356eb8219
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303410"
---
# <a name="framework-mfc"></a>Framework (MFC)

Microsoft Foundation Class (MFC) kitaplığı çerçevesiyle çalışmanız, büyük ölçüde birkaç önemli sınıfa ve çeşitli görsel C++ araçlara dayalıdır. Bazı sınıflar, Win32 uygulama programlama arabiriminin (API) büyük bir bölümünü kapsüllenir. Diğer sınıflar, belgeler, görünümler ve uygulamanın kendisi gibi uygulama kavramlarını kapsüllemez. Hala diğerleri OLE özelliklerini ve ODBC ve DAO veri erişimi işlevselliğini Kapsüller.  (DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.)

Örneğin, pencere Win32's kavramı `CWnd`MFC sınıfı tarafından kapsüllenir. Diğer bir deyişle, C++ `CWnd` adlı bir sınıf, bir Windows penceresini temsil eden `HWND` tanıtıcısını Kapsüller veya "kaydırır". Benzer şekilde, sınıf `CDialog` Win32 iletişim kutularını kapsüller.

Kapsülleme `CWnd`C++ sınıfının, örneğin, `HWND`türünde bir üye değişkeni içerdiğini ve sınıfın üye işlevlerinin bir `HWND` parametre olarak bir alan Win32 işlevlerine çağrıları kapsüllemesini sağlar. Sınıf üyesi işlevleri genellikle kapsülledikleri Win32 işleviyle aynı ada sahiptir.

## <a name="in-this-section"></a>Bu Bölümde

[SDI ve MDI](../mfc/sdi-and-mdi.md)

[Belgeler, Görünümler ve Çerçeve](../mfc/documents-views-and-the-framework.md)

[Sihirbazlar ve kaynak düzenleyicileri](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>Ilgili bölümlerde

[Framework'te Derleme](../mfc/building-on-the-framework.md)

[Framework'ün Kodunuzu Çağırması](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)

[Belge şablonları ve belge/görünüm oluşturma Işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)

[İleti İşleme ve Eşleme](../mfc/message-handling-and-mapping.md)

[Pencere Nesneleri](../mfc/window-objects.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
