---
title: Pencere Sınıflarını Kaydetme
ms.date: 11/04/2016
f1_keywords:
- WndProc
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
ms.openlocfilehash: 7c459b909a60fff2b7aeded9ea8d79a39ced24e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309089"
---
# <a name="registering-window-classes"></a>Pencere Sınıflarını Kaydetme

Pencere "sınıfları" Windows için geleneksel programlamada, windows herhangi bir sayıda oluşturulabileceği gelen bir "class" (C++ sınıfı değil) özelliklerini tanımlayın. Bu tür bir sınıf şablonu veya windows oluşturmak için model ' dir.

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Windows için geleneksel programlarda pencere sınıfı kaydı

Windows, MFC, olmadan için geleneksel bir programda bir pencereye, "Pencere yordamını" tüm iletileri işlemek veya "`WndProc`." A `WndProc` "pencere sınıfı kaydı" işlemi yoluyla bir penceresiyle ilişkilidir. Ana pencereyi kaydedilmiştir `WinMain` işlevi, ancak diğer sınıflar Windows kaydedilebilir herhangi bir uygulama. Kayıt için bir işaretçi içeren yapısı bağlıdır `WndProc` imleç, arka plan Fırça özellikleri ile birlikte çalışması ve VS. Yapısı için çağrıda sınıfının dize adı ile birlikte bir parametre olarak geçirilen `RegisterClass` işlevi. Bu nedenle, birden çok windows tarafından kayıt sınıf paylaşılabilir.

## <a name="window-class-registration-in-mfc-programs"></a>MFC programlarda pencere sınıfı kaydı

Buna karşılık, çoğu pencere sınıfı kaydı etkinliği bir MFC çerçeve programında otomatik olarak gerçekleştirilir. MFC kullanıyorsanız, genellikle bir C++ pencere sınıfı için sınıf devralma normal C++ söz dizimini kullanarak mevcut bir kitaplık sınıfından türetilir. Çerçeve hala geleneksel kullanır ve "kayıt sınıfları" için gerektiğinde kaydettiğiniz birkaç standart olanları sağlar. Ek kayıt sınıfları çağırarak kaydedebilirsiniz [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) genel işlev ve sınıfa kayıtlı başarılıdan `Create` üye işlevini `CWnd`. Burada, geleneksel açıklandığı şekilde "kayıt class" Windows içinde olan bir C++ sınıfı ile karıştırılmamalıdır.

Daha fazla bilgi için [Teknik Not 1](../mfc/tn001-window-class-registration.md).

## <a name="see-also"></a>Ayrıca bkz.

[Pencereler Oluşturma](../mfc/creating-windows.md)
