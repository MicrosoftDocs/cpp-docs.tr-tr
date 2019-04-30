---
title: Komut Yönlendirme Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.command
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
ms.openlocfilehash: 264e931ba0468cdc44f27c55e5d259948c5392b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406060"
---
# <a name="command-routing-classes"></a>Komut Yönlendirme Sınıfları

Kullanıcı fare ile denetim çubuğu düğme veya menüler seçerek uygulamayla etkileşim içinde gibi uygulamanın uygun komut hedef nesneye etkilenen kullanıcı arabirimi nesnesinden iletileri gönderir. Türetilen sınıflar komut hedefi `CCmdTarget` dahil [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), ve bunlardan türetilmiş sınıflar. Framework, böylece komutları uygulamada o anda etkin olan en uygun nesne tarafından işlenebilen otomatik komut yönlendirmeyi destekler.

Sınıfın bir nesnesi `CCmdUI` kullanıcı Arabirimi, komut hedefleri güncelleştirme komutuna geçirilir ([on_update_command_uı](reference/message-map-macros-mfc.md#on_update_command_ui)), belirli bir komut için kullanıcı arabirimi durumu güncelleştirmek izin vermek için işleyiciler (örneğin, için onay veya kaldırma denetimden menü öğeleri). Üye işlevlerini çağırın `CCmdUI` kullanıcı Arabirimi nesnesi durumunu güncelleştirmek için nesne. Belirli bir komut ile ilişkili kullanıcı Arabirimi nesnesi bir menü öğesi veya bir düğme veya her ikisini de olup bu işlemi aynıdır.

[CCmdTarget](../mfc/reference/ccmdtarget-class.md)<br/>
Alabilir ve iletileri cevaplayin nesnelerin tüm sınıflar için taban sınıf görevi görür.

[Ccmduı](../mfc/reference/ccmdui-class.md)<br/>
Menü öğeleri ya da denetim çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini güncelleştirme için bir programlama arabirimi sağlar. Komut hedef nesnesi sağlar, devre dışı bırakır, denetler ve/veya kullanıcı arabirimi nesne bu nesne temizler.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
