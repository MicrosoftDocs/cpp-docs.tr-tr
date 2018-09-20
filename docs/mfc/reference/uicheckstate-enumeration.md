---
title: Uıcheckstate numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 04/03/2017
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- afxwinforms/uicheckstate
dev_langs:
- C++
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc09dcb36d7d1ec1abd2f51fd13b6daadd74601f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403857"
---
# <a name="uicheckstate-enumeration"></a>UICheckState Numaralandırması
Bir kullanıcı arabirimi öğesi komutu için onay durumunu açıklar.

### <a name="syntax"></a>Sözdizimi

```
public enum class
{
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]
   Unchecked,
   Checked,
   Indeterminate
};
```

### <a name="remarks"></a>Açıklamalar

[ICommandUI::Check](icommandui-interface.md#check) bir kullanıcı arabirimi öğesinin durumunu tanımlamak için bu değerleri kullanır.
Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll içinde tanımlanmıştır)
