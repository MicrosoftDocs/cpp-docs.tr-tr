---
title: MSG yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b2f58af3bcf3eef524b95d25579e5bc233f9108
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334456"
---
# <a name="msg-structure"></a>MSG Yapısı

`MSG` Yapısı, bir iş parçacığının ileti kuyruğundan ileti bilgileri içerir.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagMSG {     // msg
    HWND hwnd;
    UINT message;
    WPARAM wParam;
    LPARAM lParam;
    DWORD time;
    POINT pt;
} MSG;
```

#### <a name="parameters"></a>Parametreler

*HWND*<br/>
Pencere yordamı olan iletiyi alır penceresi tanımlar.

*message*<br/>
İleti sayısını belirtir.

*wParam*<br/>
İleti hakkında ek bilgi belirtir. Tam anlamı değerine bağlıdır `message` üyesi.

*lParam*<br/>
İleti hakkında ek bilgi belirtir. Tam anlamı değerine bağlıdır `message` üyesi.

*saat*<br/>
Başlangıçtan iletinin gönderildiği saati belirtir.

*PT*<br/>
İletinin gönderildiği sırada ekran koordinatlarında imleç konumu belirtir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

