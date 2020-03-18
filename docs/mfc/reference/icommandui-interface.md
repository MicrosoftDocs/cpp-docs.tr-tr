---
title: Iommanduı arabirimi
ms.date: 09/07/2019
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
ms.openlocfilehash: a7bb3ab5ed292cef8108e937e67bc9e2ccc1ebce
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421298"
---
# <a name="icommandui-interface"></a>Iommanduı arabirimi

Kullanıcı arabirimi komutlarını yönetir.

## <a name="syntax"></a>Sözdizimi

```
interface class ICommandUI
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[icommandui__Check](#check)|Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.|
|[Iommanduı:: Devamsallama](#continuerouting)|Komut yönlendirme mekanizmasına, geçerli iletiyi işleyiciler zincirinin altına yönlendirmeye devam etmeyi söyler.|
|[Iommanduı:: etkin](#enabled)|Bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır.|
|[Iommanduı:: ID](#id)|`ICommandUI` nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin KIMLIĞINI alır.|
|[Iommanduı:: Index](#index)|`ICommandUI` nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin dizinini alır.|
|[Iommanduı:: Radio](#radio)|Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.|
|[ICommandUI:: metin](#text)|Bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, Kullanıcı arabirimi komutlarını yöneten Yöntemler ve özellikler sağlar. `ICommandUI` [CCmdUI sınıfına](../../mfc/reference/ccmdui-class.md)benzerdir, ancak bu, .NET bileşenleriyle bırlıkte çalışan MFC uygulamaları için `ICommandUI` kullanılır.

`ICommandUI`, [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)ile türetilmiş bir sınıfta bir ON_UPDATE_COMMAND_UI işleyicisi içinde kullanılır. Bir uygulamanın kullanıcısı bir menüyü etkinleştirir (seçer veya tıklatır), her menü öğesi etkin veya devre dışı olarak görüntülenir. Her menü komutunun hedefi, bir ON_UPDATE_COMMAND_UI işleyicisi uygulayarak bu bilgileri sağlar. Uygulamanızdaki her bir komut Kullanıcı arabirimi nesnesi için, her işleyici için bir ileti eşleme girişi ve işlev prototipi oluşturmak üzere [sınıf Sihirbazı](mfc-class-wizard.md) ' nı kullanın.

`ICommandUI` arabiriminin komut yönlendirmesinde nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [nasıl yapılır: komut yönlendirmesi ekleme Windows Forms denetimi](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Kullanıcı arabirimi komutlarının MFC 'de nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CCmdUI sınıfı](../../mfc/reference/ccmdui-class.md).

## <a name="check"></a>ICommandUI:: Check

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.
```
property UICheckState Check;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar. Denetimi aşağıdaki değerlere ayarlayın:
- 0 işaretini kaldır
- 1 denetim
- 2 belirsiz ayarla

## <a name="continuerouting"></a>Iommanduı:: Devamsallama

Komut yönlendirme mekanizmasına, geçerli iletiyi işleyiciler zincirinin altına yönlendirmeye devam etmeyi söyler.
```
void ContinueRouting();
```

## <a name="remarks"></a>Açıklamalar

Bu, FALSE döndüren bir ON_COMMAND_EX işleyicisiyle birlikte kullanılması gereken gelişmiş bir üye işlevdir. Daha fazla bilgi için bkz. Teknik NotTN006: Ileti haritaları.

## <a name="enabled"></a>Iommanduı:: etkin

Bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır.
```
property bool Enabled;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır. Öğeyi etkinleştirmek için TRUE olarak ayarlayın, devre dışı bırakmak için FALSE.

## <a name="id"></a>Iommanduı:: ID

Iommandui nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin KIMLIĞINI alır.
```
property unsigned int ID;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bir menü öğesi, araç çubuğu düğmesi veya ıcommandui nesnesi tarafından temsil edilen diğer kullanıcı arabirimi nesnesinin KIMLIĞINI (bir tanıtıcı) alır.

## <a name="index"></a>Iommanduı:: Index

Iommandui nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin dizinini alır.
```
property unsigned int Index;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bir menü öğesi, araç çubuğu düğmesi veya ıcommandui nesnesi tarafından temsil edilen diğer kullanıcı arabirimi nesnesinin dizinini (bir tanıtıcı) alır.

## <a name="radio"></a>Iommanduı:: Radio

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.
```
property bool Radio;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar. Öğeyi etkinleştirmek için radyoyu TRUE olarak ayarlayın; Aksi halde yanlış.

## <a name="text"></a>ICommandUI:: metin

Bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar.
```
property String^ Text;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar. Metni bir metin dizesi tutamacı olarak ayarlayın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxwinforms. h (Assembly atlmfc\lib\mfcmifc80.dll derlemesinde tanımlanmıştır)

## <a name="see-also"></a>Ayrıca bkz.

[CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)
