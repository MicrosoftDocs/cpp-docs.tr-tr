---
description: 'Hakkında daha fazla bilgi edinin: UICheckState numaralandırması'
title: UICheckState Numaralandırması
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 8c6f250dd6f6646d22aac0fa819b73537ee0f443
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218647"
---
# <a name="uicheckstate-enumeration"></a>UICheckState Numaralandırması

Komut için bir kullanıcı arabirimi öğesinin denetim durumunu açıklar.

### <a name="syntax"></a>Syntax

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

[ICommandText:: Check](icommandui-interface.md#check) , bir kullanıcı arabirimi öğesinin durumunu anlatmak için bu değerleri kullanır.
Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h (derlemede tanımlanan atlmfc\lib\mfcmifc80.dll)
