---
title: Uygulama Çerçevesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- application framework [MFC], building applications
- applications [MFC]
- application framework [MFC]
ms.assetid: 912684e6-4418-49dc-9877-a4cd19d69d20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d04e8cef4500e738fb0948574786012b8a141daf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425944"
---
# <a name="application-framework"></a>Uygulama Framework'ü

Microsoft Foundation Class (MFC) Kitaplığı'nın çekirdeği C++ formunda Windows API büyük bir kısmı sarmalanmasını olur. Windows, iletişim kutuları, cihaz bağlamları Fırçalar ve kalemler, denetimler ve diğer standart Windows öğeler gibi ortak GDI nesnelerini kitaplığı sınıflarını temsil eder. Bu sınıflar kullanışlı sağlar, bunlar kapsülleyen Windows yapılarda C++ üye işlevi arabirimi. Bu sınıflar kullanma hakkında daha fazla bilgi için bkz. [pencere nesnesi konuları](../mfc/window-objects.md).

Ancak, MFC Kitaplığı da ek uygulama işlevlerinin C++ kapsülleme Windows API üzerinde derlenmiş bir katmanı sağlar. Bir çalışan uygulama çerçevesi için en yaygın kullanıcı arabirimi sağlayan Windows yazdırma, araç çubuklarını, durum çubukları dahil olmak üzere Windows için yazdırma önizleme programlarını beklenen veritabanı desteği ve ActiveX desteği bu katmanıdır. [Yazma uygulamaları için Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md) framework ayrıntılı açıklanmaktadır.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Sınıf Tasarımı Felsefesi](../mfc/general-class-design-philosophy.md)
