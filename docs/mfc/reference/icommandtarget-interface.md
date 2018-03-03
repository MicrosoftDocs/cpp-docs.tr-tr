---
title: ICommandTarget arabirimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs:
- C++
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be8adb388bed39f91637dd1ef37ee1ee895f291d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="icommandtarget-interface"></a>ICommandTarget arabirimi
Bir kullanıcı denetimi komutlar bir komut kaynak nesneden almak için bir arabirim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ICommandTarget::Initialize'ı](#initialize)|Komut hedefi nesnesini başlatır.|  
  
## <a name="remarks"></a>Açıklamalar  
 MFC görünümü, bir kullanıcı denetimi barındırdığınızda [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yollar komutlar ve güncelleştirme komut MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemeye izin vermek için kullanıcı denetimi UI iletileri. Uygulama tarafından `ICommandTarget`, başvuru kullanıcı denetime [ICommandSource](../../mfc/reference/icommandsource-interface.md) nesnesi.  
  
 Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll tanımlanan)  
  
##  <a name="initialize"></a>ICommandTarget::Initialize'ı  
 Komut hedefi nesnesini başlatır.  
  
```  
void Initialize(ICommandSource^ cmdSource);  
```  
  
### <a name="parameters"></a>Parametreler  
 `cmdSource`  
 Komut kaynak nesnesi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 MFC görünümü olarak bir kullanıcı denetimini barındırdığınızda CWinFormsView komutlar ve güncelleştirme komut UI iletilerini MFC komutlarını işlemeye izin vermek için kullanıcı denetimi yönlendirir.  
  
 Bu yöntem komutu hedef nesnesini başlatır ve belirtilen komut kaynak nesnesi cmdSource ile ilişkilendirir. Kullanıcı denetimi sınıfı uygulamasında çağrılmalıdır. Başlatma sırasında Initialize uygulamasında arama ICommandSource::AddCommandHandler tarafından komut kaynak nesnesi ile komut işleyicileri kaydetmeniz. Bkz: nasıl yapılır: Windows Forms denetimi başlatma Bunu yapmak için nasıl kullanılacağını gösteren bir örnek komut yönlendirme ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: komut ekleme yönlendirme Windows Forms denetimi](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandSource Arabirimi](../../mfc/reference/icommandsource-interface.md)



