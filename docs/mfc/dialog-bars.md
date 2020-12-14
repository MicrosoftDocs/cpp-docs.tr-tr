---
description: 'Hakkında daha fazla bilgi edinin: Iletişim çubukları'
title: İletişim Kutusu Çubukları
ms.date: 11/19/2018
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
ms.openlocfilehash: 701954dc9ec682bd95258b26d7af1290ea2da521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261638"
---
# <a name="dialog-bars"></a>İletişim Kutusu Çubukları

İletişim çubuğu, herhangi bir tür denetimi içerebilen bir [denetim çubuğu](control-bars.md) türü olan bir araç çubuğudur. Kalıcı olmayan bir iletişim kutusunun özelliklerine sahip olduğundan, [CDialogBar](reference/cdialogbar-class.md) nesnesi daha güçlü bir araç çubuğu sağlar.

Bir araç çubuğu ile nesne arasında birkaç temel farklılık vardır `CDialogBar` . `CDialogBar`Visual C++ iletişim kutusu Düzenleyicisi ile oluşturabileceğiniz ve herhangi bir tür Windows denetimi içerebilen bir iletişim kutusu şablon kaynağından bir nesne oluşturulur. Kullanıcı denetimden denetime sekmeye kadar sekme alabilir. Ayrıca, iletişim çubuğunu üst çerçeve penceresinin herhangi bir bölümü ile hizalamak veya üst yeniden boyutlandırılırsa bile yerinde bırakmak için bir hizalama stili belirtebilirsiniz. Aşağıdaki şekilde, çeşitli denetimleri olan bir iletişim çubuğu gösterilmektedir.

![VC Iletişim çubuğu](../mfc/media/vc378t1.gif "VC Iletişim çubuğu") <br/>
Iletişim çubuğu

Başka bir durumda, bir nesneyle çalışmak `CDialogBar` kalıcı olmayan iletişim kutusuyla çalışıyor gibidir. İletişim kutusu kaynağını tasarlamak ve oluşturmak için iletişim kutusu düzenleyicisini kullanın.

İletişim çubuklarının sanallardan biri, düğme dışındaki denetimleri dahil edebilirler.

Kendi iletişim sınıflarınızı ' den türetmeye normal olsa `CDialog` da, genellikle bir iletişim çubuğu için kendi sınıfınızı türetirsiniz. İletişim çubukları, ana pencereye yönelik uzantılardır ve **BN_CLICKED** veya **EN_CHANGE** gibi tüm iletişim çubuğu denetim bildirim mesajları iletişim çubuğunun üst penceresine gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)<br/>
[Örnek](../overview/visual-cpp-samples.md)
