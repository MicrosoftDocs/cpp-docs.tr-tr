---
title: İletişim Kutusu Çubukları
ms.date: 11/19/2018
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
ms.openlocfilehash: 052e0b8a085c052f73d3c6540521f57fdfbb9c51
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624893"
---
# <a name="dialog-bars"></a>İletişim Kutusu Çubukları

İletişim çubuğu, herhangi bir tür denetimi içerebilen bir [denetim çubuğu](control-bars.md) türü olan bir araç çubuğudur. Kalıcı olmayan bir iletişim kutusunun özelliklerine sahip olduğundan, [CDialogBar](reference/cdialogbar-class.md) nesnesi daha güçlü bir araç çubuğu sağlar.

Bir araç çubuğu ile nesne arasında birkaç temel farklılık vardır `CDialogBar` . `CDialogBar`Visual C++ iletişim kutusu Düzenleyicisi ile oluşturabileceğiniz ve herhangi bir tür Windows denetimi içerebilen bir iletişim kutusu şablon kaynağından bir nesne oluşturulur. Kullanıcı denetimden denetime sekmeye kadar sekme alabilir. Ayrıca, iletişim çubuğunu üst çerçeve penceresinin herhangi bir bölümü ile hizalamak veya üst yeniden boyutlandırılırsa bile yerinde bırakmak için bir hizalama stili belirtebilirsiniz. Aşağıdaki şekilde, çeşitli denetimleri olan bir iletişim çubuğu gösterilmektedir.

![VC Iletişim çubuğu](../mfc/media/vc378t1.gif "VC Iletişim çubuğu") <br/>
Iletişim çubuğu

Başka bir durumda, bir nesneyle çalışmak `CDialogBar` kalıcı olmayan iletişim kutusuyla çalışıyor gibidir. İletişim kutusu kaynağını tasarlamak ve oluşturmak için iletişim kutusu düzenleyicisini kullanın.

İletişim çubuklarının sanallardan biri, düğme dışındaki denetimleri dahil edebilirler.

Kendi iletişim sınıflarınızı ' den türetmeye normal olsa `CDialog` da, genellikle bir iletişim çubuğu için kendi sınıfınızı türetirsiniz. İletişim çubukları, ana pencereye yönelik uzantılardır ve **BN_CLICKED** veya **EN_CHANGE**gibi tüm iletişim çubuğu denetim bildirim mesajları iletişim çubuğunun üst penceresine gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)<br/>
[Örnek](../overview/visual-cpp-samples.md)
