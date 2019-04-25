---
title: UICheckState Numaralandırması
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 1411e9b7cb088c063e17cc7c59871e5f0b83ad9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309804"
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
