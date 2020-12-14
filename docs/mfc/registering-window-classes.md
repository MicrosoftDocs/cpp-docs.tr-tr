---
description: 'Daha fazla bilgi edinin: pencere sınıflarını kaydetme'
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
ms.openlocfilehash: e31f83b691ad12d845afca6a3a5f18d9ba64b0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218200"
---
# <a name="registering-window-classes"></a>Pencere Sınıflarını Kaydetme

Windows için geleneksel programlamada pencere "sınıfları", herhangi bir sayıda Windows 'un oluşturulabilmesi için bir "sınıf" (C++ sınıfı değil) özelliklerini tanımlar. Bu tür bir sınıf, Windows oluşturmak için bir şablon veya modeldir.

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Windows için geleneksel programlarda pencere sınıfı kaydı

Windows için geleneksel bir programda MFC olmadan, tüm iletileri "pencere yordamında" veya "." içinde bir pencereye işleyebilirsiniz `WndProc` . Bir `WndProc` , "pencere sınıfı kaydı" süreci aracılığıyla bir pencere ile ilişkilendirilir. Ana pencere `WinMain` işleve kaydedilir, ancak diğer Windows sınıfları uygulamanın herhangi bir yerinde kaydedilebilir. Kayıt, `WndProc` imleç, arka plan fırçası vb. belirtimlerle birlikte işlev işaretçisini içeren bir yapıya bağımlıdır. Yapı bir parametre olarak geçirilir ve işlevin dize adı ile birlikte işleve önceki bir çağrıdadır `RegisterClass` . Bu nedenle, bir kayıt sınıfı birden çok pencere tarafından paylaşılabilir.

## <a name="window-class-registration-in-mfc-programs"></a>MFC programlarında pencere sınıfı kaydı

Buna karşılık, çoğu pencere sınıfı kayıt etkinliği bir MFC çerçeve programında otomatik olarak yapılır. MFC kullanıyorsanız, genellikle sınıf devralma için normal C++ söz dizimini kullanarak var olan bir kitaplık sınıfından C++ pencere sınıfını türetirsiniz. Framework hala geleneksel "kayıt sınıfları" kullanır ve gerektiğinde sizin için kayıtlı birkaç standart tane sağlar. Diğer kayıt sınıflarını, [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) genel işlevini çağırarak ve sonra kayıtlı sınıfı `Create` öğesinin üye işlevine geçirerek kaydedebilirsiniz `CWnd` . Burada açıklandığı gibi, Windows 'daki geleneksel "kayıt sınıfı" C++ sınıfıyla karıştırılmamalıdır.

Daha fazla bilgi için bkz. [teknik notta 1](../mfc/tn001-window-class-registration.md).

## <a name="see-also"></a>Ayrıca bkz.

[Windows oluşturma](../mfc/creating-windows.md)
