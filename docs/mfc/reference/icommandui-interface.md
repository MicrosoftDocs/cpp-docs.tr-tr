---
title: ICommandUI arabirimi | Microsoft Docs
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
ms.openlocfilehash: 70e6f1eb8848c5ee93063877ae036f66584b69c4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="icommandui-interface"></a>ICommandUI arabirimi
Kullanıcı arabirimi komutları yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[icommandui__Check](#check)|Bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar.|  
|[ICommandUI::ContinueRouting](#continuerouting)|Geçerli ileti işleyicileri zincirine aşağı yönlendirme devam etmek için komut yönlendirme mekanizması söyler.|  
|[ICommandUI::Enabled](#enabled)|Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.|  
|[ICommandUI::ID](#id)|Tarafından temsil edilen kullanıcı arabirimi nesnesinin kimliği alır `ICommandUI` nesnesi.|  
|[ICommandUI::Index](#index)|Tarafından temsil edilen kullanıcı arabirimi nesnesi dizinini alır `ICommandUI` nesnesi.|  
|[ICommandUI::Radio](#radio)|Bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar.|  
|[ICommandUI::Text](#text)|Bu komut için kullanıcı arabirimi öğesi metni ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim yöntemleri ve kullanıcı arabirimi komutları yönetmek özellikleri sağlar. `ICommandUI` benzer [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md)dışında `ICommandUI` .NET bileşenleriyle birlikte MFC uygulamalarında kullanılır.  
  
 `ICommandUI` içinde kullanılan bir `ON_UPDATE_COMMAND_UI` işleyicisinde bir [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-türetilmiş sınıf. Bir kullanıcı bir uygulamanın (seçer veya tıklama) etkinleştirdiğinde menüsünde, her bir menü öğesi etkin olarak görüntülenir veya devre dışı. Her menü komut hedefinin uygulayarak bu bilgileri sağlar. bir `ON_UPDATE_COMMAND_UI` işleyicisi. Her komut kullanıcı arabirimi nesneleri uygulamanızda için her işleyicisi için işlev prototipi ve ileti eşleme girişi oluşturmak için Özellikler penceresini kullanın.  
  
 Nasıl hakkında daha fazla bilgi için `ICommandUI` arabirimi komut yönlendirme kullanılır, bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Kullanıcı arabirimi komutları MFC'de nasıl yönetildiğini daha fazla bilgi için bkz: [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md).  
  
## <a name="check"></a> ICommandUI::Check  
Bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar.
```
property UICheckState Check;
```
## <a name="remarks"></a>Açıklamalar  
Bu özellik bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Onay için aşağıdaki değerleri ayarlayın:  
- 0 kutusunun işaretini kaldırın  
- 1 onay  
- 2 belirsiz ayarlayın  

## <a name="continuerouting"></a> ICommandUI::ContinueRouting   
Geçerli ileti işleyicileri zincirine aşağı yönlendirme devam etmek için komut yönlendirme mekanizması söyler.
```
void ContinueRouting();
```
## <a name="remarks"></a>Açıklamalar
Bu FALSE değerini döndürür bir ON_COMMAND_EX işleyicisi ile birlikte kullanılması gereken bir Gelişmiş üyelik işlevdir. Teknik Not TN006 daha fazla bilgi için bkz: ileti eşlemeleri.

## <a name="enabled"></a> ICommandUI::Enabled 
Sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır.
```
property bool Enabled;
```
## <a name="remarks"></a>Açıklamalar
Bu özellik sağlar veya bu komut için kullanıcı arabirimi öğesi devre dışı bırakır. Etkin olarak etkinleştirmek için true, öğe devre dışı bırakmak için FALSE olarak ayarlayın.

## <a name="id"></a> ICommandUI::ID  
ICommandUI nesnesiyle temsil edilen kullanıcı arabirimi nesnesinin kimliği alır.
```
property unsigned int ID;
```
## <a name="remarks"></a>Açıklamalar
Bu özellik Kimliğini (bir tanıtıcı) menü öğesi, araç çubuğu düğmesini veya ICommandUI nesnesiyle temsil edilen diğer kullanıcı arabirimi nesnesi alır.

## <a name="index"></a> ICommandUI::Index   
ICommandUI nesnesiyle temsil edilen kullanıcı arabirimi nesnesi dizinini alır.
```
property unsigned int Index;
```
## <a name="remarks"></a>Açıklamalar
Bu özellik dizinini (tanıtıcı) menü öğesi, araç çubuğu düğmesini veya ICommandUI nesnesiyle temsil edilen diğer kullanıcı arabirimi nesnesi alır.

## <a name="radio"></a> ICommandUI::Radio 
Bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar.
```
property bool Radio;
```
## <a name="remarks"></a>Açıklamalar
Bu özellik bu komut için kullanıcı arabirimi öğesi uygun onay durumuna ayarlar. Radyo etkinleştir öğesi true ayarlayın; Aksi takdirde FALSE.

## <a name="text"></a> ICommandUI::Text 
Bu komut için kullanıcı arabirimi öğesi metni ayarlar.
```
property String^ Text;
```
## <a name="remarks"></a>Açıklamalar
Bu özellik, bu komut için kullanıcı arabirimi öğesi metni ayarlar. Metni için bir metin dizesi tanıtıcı ayarlayın.

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll tanımlanan)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdUI Sınıfı](../../mfc/reference/ccmdui-class.md)
