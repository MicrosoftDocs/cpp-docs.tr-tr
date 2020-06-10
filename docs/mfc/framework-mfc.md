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
ms.openlocfilehash: b02d5a1862a278f46591895f20f58a97367b5ab2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618791"
---
# <a name="framework-mfc"></a>Framework (MFC)

Microsoft Foundation Class (MFC) kitaplığı çerçevesiyle çalışmanız, büyük ölçüde birkaç önemli sınıfa ve birkaç Visual C++ araca dayalıdır. Bazı sınıflar, Win32 uygulama programlama arabiriminin (API) büyük bir bölümünü kapsüllenir. Diğer sınıflar, belgeler, görünümler ve uygulamanın kendisi gibi uygulama kavramlarını kapsüllemez. Hala diğerleri OLE özelliklerini ve ODBC ve DAO veri erişimi işlevselliğini Kapsüller.  (DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.)

Örneğin, pencere Win32's kavramı MFC sınıfıyla kapsüllenir `CWnd` . Diğer bir deyişle, `CWnd` `HWND` bir Windows penceresini temsil eden tutamacı Kapsüller veya "sarmalanmış" olarak adlandırılan bir C++ sınıfı. Benzer şekilde, sınıf `CDialog` Win32 iletişim kutularını kapsüller.

Kapsülleme, örneğin, C++ sınıfının `CWnd` türünde bir üye değişkeni içerir `HWND` ve sınıfın üye işlevleri parametre olarak bir olarak alan Win32 işlevlerine çağrıları Kapsüller `HWND` . Sınıf üyesi işlevleri genellikle kapsülledikleri Win32 işleviyle aynı ada sahiptir.

## <a name="in-this-section"></a>Bu Bölümde

[SDI ve MDI](sdi-and-mdi.md)

[Belgeler, Görünümler ve Çerçeve](documents-views-and-the-framework.md)

[Sihirbazlar ve kaynak düzenleyicileri](wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>Ilgili bölümlerde

[Framework'te Derleme](building-on-the-framework.md)

[Framework'ün Kodunuzu Çağırması](how-the-framework-calls-your-code.md)

[CWinApp: Uygulama Sınıfı](cwinapp-the-application-class.md)

[Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi](document-templates-and-the-document-view-creation-process.md)

[İleti İşleme ve Eşleme](message-handling-and-mapping.md)

[Pencere nesneleri](window-objects.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](using-the-classes-to-write-applications-for-windows.md)
