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
ms.openlocfilehash: 0c185e873f526403e86cb5a80f6e0631f8654284
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743444"
---
# <a name="icommandui-interface"></a>Iommanduı arabirimi

Kullanıcı arabirimi komutlarını yönetir.

## <a name="syntax"></a>Syntax

```
interface class ICommandUI
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[icommandui__Check](#check)|Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.|
|[Iommanduı:: Devamsallama](#continuerouting)|Komut yönlendirme mekanizmasına, geçerli iletiyi işleyiciler zincirinin altına yönlendirmeye devam etmeyi söyler.|
|[Iommanduı:: etkin](#enabled)|Bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır.|
|[Iommanduı:: ID](#id)|Nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin KIMLIĞINI alır `ICommandUI` .|
|[Iommanduı:: Index](#index)|Nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin dizinini alır `ICommandUI` .|
|[Iommanduı:: Radio](#radio)|Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.|
|[ICommandUI:: metin](#text)|Bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar.|

### <a name="remarks"></a>Açıklamalar

Bu arabirim, Kullanıcı arabirimi komutlarını yöneten Yöntemler ve özellikler sağlar. `ICommandUI` , [CCmdUI sınıfına](../../mfc/reference/ccmdui-class.md)benzerdir, ancak `ICommandUI` .net BILEŞENLERIYLE birlikte çalışan MFC uygulamaları için kullanılır.

`ICommandUI` , bir [ICommandText](../../mfc/reference/icommandtarget-interface.md)içinde türetilmiş bir sınıfta ON_UPDATE_COMMAND_UI işleyicisi içinde kullanılır. Bir uygulamanın kullanıcısı bir menüyü etkinleştirir (seçer veya tıklatır), her menü öğesi etkin veya devre dışı olarak görüntülenir. Her menü komutunun hedefi, bir ON_UPDATE_COMMAND_UI işleyicisi uygulayarak bu bilgileri sağlar. Uygulamanızdaki her bir komut Kullanıcı arabirimi nesnesi için, her işleyici için bir ileti eşleme girişi ve işlev prototipi oluşturmak üzere [sınıf Sihirbazı](mfc-class-wizard.md) ' nı kullanın.

Arabirimin komut yönlendirmesinde nasıl kullanıldığı hakkında daha fazla bilgi için `ICommandUI` bkz. [nasıl yapılır: komut yönlendirmesi ekleme Windows Forms denetimi](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Kullanıcı arabirimi komutlarının MFC 'de nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CCmdUI sınıfı](../../mfc/reference/ccmdui-class.md).

## <a name="icommanduicheck"></a><a name="check"></a> ICommandUI:: Check

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.

```
property UICheckState Check;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar. Denetimi aşağıdaki değerlere ayarlayın:

- 0 işaretini kaldır
- 1 denetim
- 2 belirsiz ayarla

## <a name="icommanduicontinuerouting"></a><a name="continuerouting"></a> Iommanduı:: Devamsallama

Komut yönlendirme mekanizmasına, geçerli iletiyi işleyiciler zincirinin altına yönlendirmeye devam etmeyi söyler.

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>Açıklamalar

Bu, FALSE döndüren bir ON_COMMAND_EX işleyicisiyle birlikte kullanılması gereken gelişmiş bir üye işlevdir. Daha fazla bilgi için bkz. Teknik NotTN006: Ileti haritaları.

## <a name="icommanduienabled"></a><a name="enabled"></a> Iommanduı:: etkin

Bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır.

```
property bool Enabled;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini etkinleştirilir veya devre dışı bırakır. Öğeyi etkinleştirmek için TRUE olarak ayarlayın, devre dışı bırakmak için FALSE.

## <a name="icommanduiid"></a><a name="id"></a> Iommanduı:: ID

Iommandui nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin KIMLIĞINI alır.

```
property unsigned int ID;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bir menü öğesi, araç çubuğu düğmesi veya ıcommandui nesnesi tarafından temsil edilen diğer kullanıcı arabirimi nesnesinin KIMLIĞINI (bir tanıtıcı) alır.

## <a name="icommanduiindex"></a><a name="index"></a> Iommanduı:: Index

Iommandui nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin dizinini alır.

```
property unsigned int Index;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bir menü öğesi, araç çubuğu düğmesi veya ıcommandui nesnesi tarafından temsil edilen diğer kullanıcı arabirimi nesnesinin dizinini (bir tanıtıcı) alır.

## <a name="icommanduiradio"></a><a name="radio"></a> Iommanduı:: Radio

Bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.

```
property bool Radio;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar. Öğeyi etkinleştirmek için radyoyu TRUE olarak ayarlayın; Aksi halde yanlış.

## <a name="icommanduitext"></a><a name="text"></a> ICommandUI:: metin

Bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar.

```
property String^ Text;
```

### <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için Kullanıcı arabirimi öğesinin metnini ayarlar. Metni bir metin dizesi tutamacı olarak ayarlayın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h (derlemede tanımlanan atlmfc\lib\mfcmifc80.dll)

## <a name="see-also"></a>Ayrıca bkz.

[CCmdUI sınıfı](../../mfc/reference/ccmdui-class.md)
