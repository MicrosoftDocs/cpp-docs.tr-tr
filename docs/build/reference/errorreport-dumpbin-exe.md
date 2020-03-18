---
title: /ERRORREPORT (dumpbin.exe)
description: Microsoft DUMPBIN yardımcı programı/ERRORREPORT komut satırı seçeneği için başvuru.
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT_dumpbin
helpviewer_keywords:
- -ERRORREPORT dumpbin option
- ERRORREPORT dumpbin option
- /ERRORREPORT dumpbin option
ms.assetid: 51178c43-4f95-4fda-8f97-50a257d1c948
ms.openlocfilehash: f701c2e28dcf82194589877709bf6959de4bcbfc
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439938"
---
# <a name="errorreport-dumpbinexe"></a>/ERRORREPORT (dumpbin.exe)

> [!NOTE]
> /ERRORREPORT seçeneği kullanım dışıdır. Windows Vista 'Dan başlayarak hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir.

## <a name="syntax"></a>Sözdizimi

> **/Errorreport**\[**NONE** \| **Prompt** \| **kuyruğu** \| **Gönder** ]

## <a name="remarks"></a>Açıklamalar

**/Errorreport** bağımsız değişkenleri Windows hata bildirimi hizmet ayarları tarafından geçersiz kılınır. Raporlama Windows Hata Bildirimi tarafından etkinleştirilmişse, DUMPBIN, iç hataların raporlarını otomatik olarak Microsoft 'a gönderir. Windows Hata Bildirimi tarafından devre dışı bırakıldığında hiçbir rapor gönderilmez.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
