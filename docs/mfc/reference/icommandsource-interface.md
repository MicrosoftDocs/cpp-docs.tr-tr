---
title: ICommandSource arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
dev_langs:
- C++
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ff57ec9deea4ff8b39e572d720ad7e0fdaa15dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="icommandsource-interface"></a>ICommandSource arabirimi
Bir kullanıcı denetimi için bir komut kaynak nesneden gönderilen komutları yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Bir komut işleyici için bir komut kaynak nesnesi ekler.|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Komut işleyicileri bir grup için bir komut kaynak nesnesi ekler.|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Kullanıcı arabirimi komutu ileti işleyicileri bir grup için bir komut kaynak nesnesi ekler.|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Bir kullanıcı arabirimi komutu ileti işleyicisi için bir komut kaynak nesnesi ekler.|  
|[ICommandSource::PostCommand](#postcommand)|Bu işlenmeyi bekleyen olmadan bir ileti gönderir.|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Bir komut işleyici komutu kaynak nesnesinden kaldırır.|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Komut işleyicileri bir grup komutu kaynak nesnesinden kaldırır.|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Bir grup kullanıcı arabirimi komutu ileti işleyicileri komutu kaynak nesnesinden kaldırır.|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Bir kullanıcı arabirimi komutu ileti işleyicisi komutu kaynak nesnesinden kaldırır.|  
|[ICommandSource::SendCommand](#sendcommand)|Bir ileti gönderir ve döndürmeden önce işlenecek bekler.|  
  
### <a name="remarks"></a>Açıklamalar  
 MFC görünümü, bir kullanıcı denetimi barındırdığınızda [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md) yollar komutlar ve güncelleştirme komut MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemeye izin vermek için kullanıcı denetimi UI iletileri. Uygulama tarafından [ICommandTarget arabirimi](../../mfc/reference/icommandtarget-interface.md), başvuru kullanıcı denetime `ICommandSource` nesnesi.  
  
 Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll tanımlanan)  
  
## <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler
Bir komut işleyici için bir komut kaynak nesnesi ekler.
```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler  
`cmdID`  
Komut kimliği.  
`cmdHandler`  
Komut işleyici yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar
Bu yöntem, komut işleyici cmdHandler komut kaynak nesnesi ekler ve cmdID için işleyici eşlemeleri.
Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) AddCommandHandler kullanma örneği.

## <a name="addcommandrangehandler"></a> ICommandSource::AddCommandRangeHandler

Komut işleyicileri bir grup için bir komut kaynak nesnesi ekler.
```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```
### <a name="parameters"></a>Parametreler  
`cmdIDMin`  
Komut Kimliği aralığın başlangıç dizini.
`cmdIDMax`  
Komut Kimliği aralığı bitiş dizini.
`cmdHandler`  
Komutları eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.
### <a name="remarks"></a>Açıklamalar
Bu yöntem için tek bir ileti işleyicisi komut kimlikleri bitişik bir dizi eşler ve komut kaynak nesnesi ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.

## <a name="addcommandrangeuihandler"></a> ICommandSource::AddCommandRangeUIHandler
Kullanıcı arabirimi komutu ileti işleyicileri bir grup için bir komut kaynak nesnesi ekler.
```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin, 
    unsigned int cmdIDMax, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>Parametreler  
`cmdIDMin`  
Komut Kimliği aralığın başlangıç dizini.
`cmdIDMax`  
Komut Kimliği aralığı bitiş dizini.
`cmdHandler`  
Komutları eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar
Bu yöntem için tek bir kullanıcı arabirimi komutu ileti işleyicisi komut kimlikleri bitişik bir dizi eşler ve komut kaynak nesnesi ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.

## <a name="addcommanduihandler"></a> ICommandSource::AddCommandUIHandler
Bir kullanıcı arabirimi komutu ileti işleyicisi için bir komut kaynak nesnesi ekler.
```
void AddCommandUIHandler(
    unsigned int cmdID, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>Parametreler
`cmdID`  
Komut kimliği.  
`cmdUIHandler`  
Kullanıcı arabirimi komutu ileti işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar
Bu yöntem, kullanıcı arabirimi komutu ileti işleyicisi cmdHandler komut kaynak nesnesi ekler ve cmdID için işleyici eşlemeleri.

## <a name="postcommand"></a> ICommandSource::PostCommand
Bu işlenmeyi bekleyen olmadan bir ileti gönderir.
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>Parametreler
`command`  
İletinin postalama komut kimliği.
### <a name="remarks"></a>Açıklamalar
Bu yöntem komutu tarafından belirtilen kimliği eşlenmiş iletisini zaman uyumsuz olarak gönderir. Pencere iletisi sıraya ileti yerleştirmek için CWnd::PostMessage çağırır ve iletiyi işlemek karşılık gelen pencerenin beklemeden döndürür.


## <a name="removecommandhandler"></a> ICommandSource::RemoveCommandHandler
Bir komut işleyici komutu kaynak nesnesinden kaldırır.
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Parametreler
`cmdID`  
Komut kimliği.
### <a name="remarks"></a>Açıklamalar
Bu yöntem için cmdID komutu kaynak nesneden eşlenen komut işleyici kaldırır.


## <a name="removecommandrangecommandhandler"></a> ICommandSource::RemoveCommandRangeHandler 
Komut işleyicileri bir grup komutu kaynak nesnesinden kaldırır.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>Parametreler
`cmdIDMin`  
Komut Kimliği aralığın başlangıç dizini.
`cmdIDMax`  
Komut Kimliği aralığı bitiş dizini.
### <a name="remarks"></a>Açıklamalar
Bu yöntem, bir grup için komut kimlikleri belirtilen komutu kaynak nesneden cmdIDMin ve cmdIDMax, tarafından eşlenen ileti işleyicileri kaldırır.

## <a name="removecommandrangeuihandler"></a> ICommandSource::RemoveCommandRangeUIHandler 
Bir grup kullanıcı arabirimi komutu ileti işleyicileri komutu kaynak nesnesinden kaldırır.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>Parametreler
`cmdIDMin`  
Komut Kimliği aralığın başlangıç dizini.
`cmdIDMax`  
Komut Kimliği aralığı bitiş dizini.
### <a name="remarks"></a>Açıklamalar
Bu yöntem için komut kimlikleri belirtilen komutu kaynak nesneden cmdIDMin ve cmdIDMax, tarafından eşlenen kullanıcı arabirimi komutu ileti işleyicileri, bir grup kaldırır.

## <a name="removecommanduihandler"></a> ICommandSource::RemoveCommandUIHandler 
Bir kullanıcı arabirimi komutu ileti işleyicisi komutu kaynak nesnesinden kaldırır.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Parametreler
`cmdID`  
Komut kimliği.
### <a name="remarks"></a>Açıklamalar
Bu yöntem için cmdID komutu kaynak nesneden eşlenen kullanıcı arabirimi komutu ileti işleyicisi kaldırır.

## <a name="sendcommand"></a> ICommandSource::SendCommand 
Bir ileti gönderir ve döndürmeden önce işlenecek bekler.
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>Parametreler
`command`  
Gönderilecek ileti komut kimliği.
### <a name="remarks"></a>Açıklamalar
Bu yöntem, zaman uyumlu olarak komutu tarafından belirtilen kimliği eşlenmiş iletisi gönderir. Pencere iletisi sıraya ileti yerleştirmek için CWnd::SendMessage çağırır ve bu pencere yordamı döndürmeden önce iletiyi işleyene kadar bekler.
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: komut ekleme yönlendirme Windows Forms denetimi](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget Arabirimi](../../mfc/reference/icommandtarget-interface.md)
