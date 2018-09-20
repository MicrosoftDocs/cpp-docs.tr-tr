---
title: MSG yapısı1 | Microsoft Docs
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
ms.openlocfilehash: 2819faa25e2dbd41d6578d60780d13011bb645c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388400"
---
# <a name="msg-structure1"></a>MSG yapısı1

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

