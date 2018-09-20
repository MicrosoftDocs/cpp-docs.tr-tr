---
title: ATL önceden tanımlanmış semboller | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 965eb339295b86c223b5081dede8e33dd282b95d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386606"
---
# <a name="atl-predefined-symbols"></a>ATL Önceden Tanımlanmış Semboller

Bu simgeleri ATL üstbilgi dosyalarında tanımlanır, ancak standart Windows uygulama işlevler ve Eylemler destekler. Bu simgeler, iletişim kutuları ağırlıklı olarak kullanılır. Çalışırken iletişim kutuları ve denetimleri ile de [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md), bu simgeler görünür **özellikleri** ortak denetimleri ile ilişkili penceresi. Örneği için iletişim kutusu varsa bir **iptal** düğmesini komut IDCANCEL sembolü ile ilişkilendirilmesi, [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

|||
|-|-|
|IDABORT|Denetim: İletişim kutusunda İptal düğmesi|
|IDC_STATIC|Denetimi: Statik denetim|
|IDCANCEL|Denetim: İletişim kutusunda İptal düğmesi|
|IDIGNORE|Denetim: İletişim kutusu yoksay düğmesi|
|IDNO|Denetim: İletişim kutusu düğmesi yok|
|IDOK|Denetim: İletişim kutusunda Tamam düğmesi|
|IDR_ACCELERATOR1|Kaynak: Hızlandırıcı tablosu|
|IDRETRY|Denetim: İletişim kutusunu yeniden dene düğmesi|
|IDS_PROJNAME|Dizesi: Geçerli uygulama adı|
|IDYES|Denetimi: Button iletişim kutusu Evet|

## <a name="requirements"></a>Gereksinimler

ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)<br/>
[Semboller: Kaynak Tanımlayıcıları](../windows/symbols-resource-identifiers.md)