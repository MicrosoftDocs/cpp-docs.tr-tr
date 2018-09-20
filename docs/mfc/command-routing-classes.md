---
title: Komut yönlendirme sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.command
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b467a85aca4bb1d0405f9bbddee5cb5e4f5b790
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391557"
---
# <a name="command-routing-classes"></a>Komut Yönlendirme Sınıfları

Kullanıcı fare ile denetim çubuğu düğme veya menüler seçerek uygulamayla etkileşim içinde gibi uygulamanın uygun komut hedef nesneye etkilenen kullanıcı arabirimi nesnesinden iletileri gönderir. Türetilen sınıflar komut hedefi `CCmdTarget` dahil [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), ve bunlardan türetilmiş sınıflar. Framework, böylece komutları uygulamada o anda etkin olan en uygun nesne tarafından işlenebilen otomatik komut yönlendirmeyi destekler.

Sınıfın bir nesnesi `CCmdUI` kullanıcı Arabirimi, komut hedefleri güncelleştirme komutuna geçirilir ([on_update_command_uı](reference/message-map-macros-mfc.md#on_update_command_ui)), belirli bir komut için kullanıcı arabirimi durumu güncelleştirmek izin vermek için işleyiciler (örneğin, için onay veya kaldırma denetimden menü öğeleri). Üye işlevlerini çağırın `CCmdUI` kullanıcı Arabirimi nesnesi durumunu güncelleştirmek için nesne. Belirli bir komut ile ilişkili kullanıcı Arabirimi nesnesi bir menü öğesi veya bir düğme veya her ikisini de olup bu işlemi aynıdır.

[CCmdTarget](../mfc/reference/ccmdtarget-class.md)<br/>
Alabilir ve iletileri cevaplayin nesnelerin tüm sınıflar için taban sınıf görevi görür.

[Ccmduı](../mfc/reference/ccmdui-class.md)<br/>
Menü öğeleri ya da denetim çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini güncelleştirme için bir programlama arabirimi sağlar. Komut hedef nesnesi sağlar, devre dışı bırakır, denetler ve/veya kullanıcı arabirimi nesne bu nesne temizler.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

