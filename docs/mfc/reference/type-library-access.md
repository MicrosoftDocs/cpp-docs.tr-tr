---
title: Tür kitaplığı erişimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afba5d2c2d0cd0b84e12cbd13cedba473b535587
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885903"
---
# <a name="type-library-access"></a>Tür Kitaplığı Erişimi
Tür kitaplıkları OLE kullanan diğer uygulamalar için bir OLE denetim arabirimleri kullanıma sunar. Bir veya daha fazla arabirim sağlamak olması durumunda her bir OLE denetimi tür kitaplığı olması gerekir.  
  
 Aşağıdaki makroları, kendi tür kitaplığı erişimi sağlamak bir OLE denetimi izin ver:  
  
### <a name="type-library-access"></a>Tür Kitaplığı Erişimi  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Bildiren bir `GetTypeLib` (sınıf bildirimi içinde kullanılmalıdır) bir OLE denetim üye işlevi.|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Uygulayan bir `GetTypeLib` (sınıfı uygulamasında kullanılmalıdır) bir OLE denetim üye işlevi.|  
  
##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB  
 Bildirir `GetTypeLib` denetim sınıfınızın bir üye işlevi.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *$class_name*  
 Tür kitaplığına ilgili denetim sınıfı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro denetim sınıf üstbilgi dosyasında kullanın.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB  
 Denetimin uygulayan `GetTypeLib` üye işlevi.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>Parametreler  
 *$class_name*  
 Tür kitaplığına ilgili denetim sınıfı adı.  
  
 *tlid*  
 Tür kitaplığını kimliği sayısı.  
  
 *wVerMajor*  
 Tür kitaplığı ana sürüm numarası.  
  
 *wVerMinor*  
 Tür kitaplığı ikincil sürüm numarası.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro, declare_oletypelıb makrosu kullanan herhangi bir denetim sınıf için uygulama dosyasında yer almalıdır.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
   
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
