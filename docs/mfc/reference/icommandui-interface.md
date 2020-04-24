---
title: ICommandUI Arabirimi
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
ms.openlocfilehash: b75509beb7287fad5e51dc9d15fc3e47cacf6854
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751314"
---
# <a name="icommandui-interface"></a>ICommandUI Arabirimi

Kullanıcı arabirimi komutlarını yönetir.

## <a name="syntax"></a>Sözdizimi

```
interface class ICommandUI
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[icommandui__Check](#check)|Bu komutiçin kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.|
|[ICommandUI::DevamROuting](#continuerouting)|Komut yönlendirme mekanizmasını, geçerli iletiyi işleyiciler zincirinden yönlendirmeye devam etmesini söyler.|
|[ICommandUI::Etkin](#enabled)|Bu komut için kullanıcı arabirimi öğesini etkinleştirir veya devre dışı kılabilir.|
|[ICommandUI::ID](#id)|`ICommandUI` Nesne tarafından temsil edilen kullanıcı arabirimi nesnesinin kimliğini alır.|
|[ICommandUI::Dizin](#index)|Nesne tarafından temsil edilen kullanıcı arabirimi `ICommandUI` nesnesinin dizinini alır.|
|[ICommandUI::Radyo](#radio)|Bu komutiçin kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.|
|[ICommandUI::Metin](#text)|Bu komut için kullanıcı arabirim öğesinin metnini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, kullanıcı arabirimi komutlarını yöneten yöntemler ve özellikler sağlar. `ICommandUI`.NET bileşenleriyle birlikte çalışan MFC `ICommandUI` uygulamaları için kullanılanlar dışında [CCmdUI Sınıfına](../../mfc/reference/ccmdui-class.md)benzer.

`ICommandUI`[iCommandTarget](../../mfc/reference/icommandtarget-interface.md)türetilmiş sınıfta ON_UPDATE_COMMAND_UI bir işleyici içinde kullanılır. Bir uygulamanın kullanıcısı bir menüyü etkinleştirdiğinde (seçer veya tıklattığında), her menü öğesi etkin veya devre dışı bırakılmış olarak görüntülenir. Her menü komutunun hedefi, bir ON_UPDATE_COMMAND_UI işleyicisi uygulayarak bu bilgileri sağlar. Uygulamanızdaki komut kullanıcı arabirimi nesnelerinin her biri için, her işleyici için bir ileti eşlemi girişi ve işlev prototipi oluşturmak için [Sınıf Sihirbazı'nı](mfc-class-wizard.md) kullanın.

`ICommandUI` Arabirimin komut yönlendirmesinde nasıl kullanıldığı hakkında daha fazla bilgi için [bkz.](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

Kullanıcı arabirimi komutlarının MFC'de nasıl yönetildiği hakkında daha fazla bilgi için [Bkz.](../../mfc/reference/ccmdui-class.md)

## <a name="icommanduicheck"></a><a name="check"></a>ICommandUI::Kontrol Et

Bu komutiçin kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.

```
property UICheckState Check;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirim öğesini uygun denetim durumuna ayarlar. Denetimi aşağıdaki değerlere ayarlama:

- 0 Çeki
- 1 Kontrol edin
- 2 Belirsiz ayarlayın

## <a name="icommanduicontinuerouting"></a><a name="continuerouting"></a>ICommandUI::DevamROuting

Geçerli iletiyi işleyiciler zincirinden yönlendirmeye devam etmesi için komut yönlendirme mekanizmasını söyler.

```cpp
void ContinueRouting();
```

## <a name="remarks"></a>Açıklamalar

Bu, FALSE döndüren bir ON_COMMAND_EX işleyicisi ile birlikte kullanılması gereken gelişmiş bir üye işlevdir. Daha fazla bilgi için Teknik Not TN006: İleti Haritaları'na bakın.

## <a name="icommanduienabled"></a><a name="enabled"></a>ICommandUI::Etkin

Bu komut için kullanıcı arabirimi öğesini etkinleştirir veya devre dışı kılabilir.

```
property bool Enabled;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirimi öğesini etkinleştirer veya devre dışı kılabilir. Öğeyi etkinleştirmek için TRUE'ya, FALSE'nin devre dışı bırakmasını ayarlayın.

## <a name="icommanduiid"></a><a name="id"></a>ICommandUI::ID

ICommandUI nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin kimliğini alır.

```
property unsigned int ID;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, menü öğesinin, araç çubuğu düğmesinin veya ICommandUI nesnesi tarafından temsil edilen diğer kullanıcı arabirimi nesnesinin kimliğini (tutamacını) alır.

## <a name="icommanduiindex"></a><a name="index"></a>ICommandUI::Dizin

ICommandUI nesnesi tarafından temsil edilen kullanıcı arabirimi nesnesinin dizinini alır.

```
property unsigned int Index;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, menü öğesinin, araç çubuğu düğmesinin veya ICommandUI nesnesi tarafından temsil edilen diğer kullanıcı arabirimi nesnesinin dizinin (tutamacını) alır.

## <a name="icommanduiradio"></a><a name="radio"></a>ICommandUI::Radyo

Bu komutiçin kullanıcı arabirimi öğesini uygun denetim durumuna ayarlar.

```
property bool Radio;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirim öğesini uygun denetim durumuna ayarlar. Öğeyi etkinleştirmek için Radyo'yu TRUE olarak ayarlayın; aksi takdirde YANLIŞ.

## <a name="icommanduitext"></a><a name="text"></a>ICommandUI::Metin

Bu komut için kullanıcı arabirim öğesinin metnini ayarlar.

```
property String^ Text;
```

## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirim öğesinin metnini ayarlar. Metin'i metin dize koluna ayarlayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (montaj atlmfc\lib\mfcmifc80.dll tanımlanır)

## <a name="see-also"></a>Ayrıca bkz.

[CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)
