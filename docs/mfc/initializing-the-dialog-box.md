---
title: İletişim kutusunu başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42526eea184cb4f28d5214fe0c56281ac6da9d6c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426113"
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma

Sonra iletişim kutusunu ve tüm alt denetimleri oluşturulur ancak yalnızca önce iletişim kutusu (ya da türünde) iletişim nesnesi 's ekranda [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) üye işlevi çağrılır. Kalıcı bir iletişim kutusu için bu sistemdeki `DoModal` çağırın. Kalıcı olmayan iletişim kutusu, `OnInitDialog` aldığında çağrılan `Create` çağrılır. Genellikle geçersiz kılma `OnInitDialog` ilk metin düzenleme kutusu ayarlama gibi iletişim kutusunun denetimleri başlatılamadı. Çağırmalısınız `OnInitDialog` temel sınıfının üye işlevinde `CDialog`, gelen, `OnInitDialog` geçersiz kılar.

İletişim kutusunun arka plan rengini (ve, uygulamanızdaki tüm diğer iletişim kutuları) ayarlamak istiyorsanız, bkz. [iletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

