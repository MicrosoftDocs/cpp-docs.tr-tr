---
title: Pencere sınıflarını kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WndProc
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00e397f8880f6f42f1930e668b64d3ba62eb2c64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379754"
---
# <a name="registering-window-classes"></a>Pencere Sınıflarını Kaydetme
Pencere "sınıfları" Windows için geleneksel programlamada windows herhangi bir sayıda oluşturulabileceği gelen bir "sınıf" (C++ sınıfı değil) özelliklerini tanımlayın. Bu sınıf bir şablonu veya windows oluşturmak için model türüdür.  
  
## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Windows için geleneksel programlarda pencere sınıfı kaydı  
 MFC, olmadan Windows için geleneksel bir programda kendi "Pencere yordamı" penceresinde tüm iletileri işleme veya "**WndProc**." A **WndProc** "pencere sınıfı kaydı" işlemi yoluyla bir pencere ile ilişkilidir. Ana pencerede kaydedilir `WinMain` işlevi, ancak diğer sınıflar Windows kaydedilebilir herhangi bir yerden uygulama. Kayıt için bir işaretçi içeren bir yapısı bağımlı **WndProc** belirtimleri arka planı fırçasını imleci için birlikte çalışır ve benzeri. Yapı önceki çağrıda sınıfının dize adı ile birlikte bir parametre olarak geçirilen **RegisterClass** işlevi. Bu nedenle, bir kayıt sınıfın birden çok windows tarafından paylaşılabilir.  
  
## <a name="window-class-registration-in-mfc-programs"></a>MFC programlarda pencere sınıfı kaydı  
 Buna karşılık, çoğu pencere sınıfı kaydı etkinliği bir MFC çerçevesi programında otomatik olarak yapılır. MFC kullanıyorsanız, genellikle bir C++ pencere sınıfı için sınıf devralma normal C++ söz dizimini kullanarak var olan bir kitaplık sınıfından türetilir. Çerçeve hala geleneksel kullanır "kayıt sınıfları" ve onu sizin için gerekli olduğunda kayıtlı birkaç standart olanları sağlar. Ek kayıt sınıfları çağırarak kaydedebilirsiniz [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) genel işlev ve kayıtlı sınıf geçirme **oluşturma** üye işlevini `CWnd`. Burada, geleneksel açıklandığı gibi "kayıt" Windows sınıftır C++ sınıf ile karıştırılmamalıdır.  
  
 Daha fazla bilgi için bkz: [Teknik Not 1](../mfc/tn001-window-class-registration.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencereler Oluşturma](../mfc/creating-windows.md)

