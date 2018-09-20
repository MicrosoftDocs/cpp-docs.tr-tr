---
title: Icommanduı arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ec76a554068dbec050078a0e0558cecd583410c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429219"
---
# <a name="icommandui-interface"></a>Icommanduı arabirimi

Kullanıcı arabirimi komutları yönetir.

## <a name="syntax"></a>Sözdizimi

```
interface class ICommandUI
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[icommandui__Check](#check)|Bu komut için kullanıcı arabirimi öğesi için uygun onay durumunu ayarlar.|
|[ICommandUI::ContinueRouting](#continuerouting)|Aşağı zinciri işleyicileri geçerli ileti yönlendirme devam etmek için komut yönlendirme mekanizması söyler.|
|[ICommandUI::Enabled](#enabled)|Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.|
|[ICommandUI::ID](#id)|Tarafından temsil edilen kullanıcı arabirimi nesnesi Kimliğini alır `ICommandUI` nesne.|
|[ICommandUI::Index](#index)|Tarafından temsil edilen kullanıcı arabirimi nesnesi indisini alır `ICommandUI` nesne.|
|[ICommandUI::Radio](#radio)|Bu komut için kullanıcı arabirimi öğesi için uygun onay durumunu ayarlar.|
|[ICommandUI::Text](#text)|Bu komut için kullanıcı arabirimi öğesinin metin ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, yöntemleri ve kullanıcı arabirimi komutlarını Yönet özellikleri sağlar. `ICommandUI` benzer [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md)dışında `ICommandUI` .NET bileşenleri ile birlikte çalışmak MFC uygulamaları için kullanılır.

`ICommandUI` on_update_command_uı işleyicisinde içinde kullanılan bir [Icommandtarget'a](../../mfc/reference/icommandtarget-interface.md)-türetilmiş sınıf. Bir uygulamanın kullanıcı (seçer veya tıklama) etkinleştirirken her bir menü öğesi bir menü etkin olarak görüntülenen veya devre dışı. Her menü komut hedefinin on_update_command_uı işleyici uygulayarak bu bilgileri sağlar. Her komut kullanıcı arabirimi nesnelerinin uygulamanızdaki bir ileti eşleme girişi ve işlev prototipi her işleyicisi oluşturmak için Özellikler penceresini kullanın.

İlgili daha fazla bilgi için `ICommandUI` arabirimi komut yönlendirme olarak kullanılır, bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme Ekle](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Kullanıcı arabirimi komutları MFC'de nasıl yönetildiği hakkında daha fazla bilgi için bkz. [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md).

## <a name="check"></a> ICommandUI::Check

Bu komut için kullanıcı arabirimi öğesi için uygun onay durumunu ayarlar.
```
property UICheckState Check;
```
## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Onay için aşağıdaki değerleri ayarlayın:
- 0 işaretini kaldırın
- 1 onay
- 2 belirsiz ayarlayın

## <a name="continuerouting"></a> ICommandUI::ContinueRouting

Aşağı zinciri işleyicileri geçerli ileti yönlendirme devam etmek için komut yönlendirme mekanizması söyler.
```
void ContinueRouting();
```
## <a name="remarks"></a>Açıklamalar

FALSE döndüren bir ON_COMMAND_EX işleyicisi ile birlikte kullanılması gereken bir Gelişmiş üye işlev budur. Daha fazla bilgi için bkz. Teknik Not TN006: ileti eşlemeleri.

## <a name="enabled"></a> ICommandUI::Enabled

Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.
```
property bool Enabled;
```
## <a name="remarks"></a>Açıklamalar

Bu özelliği etkinleştirir veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır. Etkin olarak etkinleştirmek için true öğe devre dışı bırakmak için FALSE olarak ayarlayın.

## <a name="id"></a> ICommandUI::ID

Icommanduı nesnesiyle temsil edilen kullanıcı arabirimi nesnesi Kimliğini alır.
```
property unsigned int ID;
```
## <a name="remarks"></a>Açıklamalar

Bu özellik, ' % s'kimliği (tanıtıcısı) menü öğesi, araç çubuğu düğmesini veya Icommanduı nesnesiyle temsil edilen diğer kullanıcı arabirimi nesnesi alır.

## <a name="index"></a> ICommandUI::Index

Icommanduı nesnesiyle temsil edilen kullanıcı arabirimi nesnesi dizinini alır.
```
property unsigned int Index;
```
## <a name="remarks"></a>Açıklamalar

Bu özellik, ' % s'dizini (bir tanıtıcı) menü öğesi, araç çubuğu düğmesini veya Icommanduı nesnesiyle temsil edilen diğer kullanıcı arabirimi nesnesi alır.

## <a name="radio"></a> ICommandUI::Radio

Bu komut için kullanıcı arabirimi öğesi için uygun onay durumunu ayarlar.
```
property bool Radio;
```
## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Radyo öğesi etkinleştirilecekse ayarlayın. Aksi durumda FALSE.

## <a name="text"></a> ICommandUI::Text

Bu komut için kullanıcı arabirimi öğesinin metin ayarlar.
```
property String^ Text;
```
## <a name="remarks"></a>Açıklamalar

Bu özellik, bu komut için kullanıcı arabirimi öğesinin metin ayarlar. Metni için metin dizesi tanıtıcı ayarlayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll içinde tanımlanmıştır)

## <a name="see-also"></a>Ayrıca Bkz.

[CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)
