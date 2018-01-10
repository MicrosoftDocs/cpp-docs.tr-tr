---
title: "Tür kitaplığı erişimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbc5ceabe60d7ee15d85495bb1a431955a589849
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="type-library-access"></a>Tür Kitaplığı Erişimi
Tür kitaplıkları OLE kullanan diğer uygulamalar için bir OLE denetiminin arabirimleri kullanıma sunar. Açığa çıkarılması bir veya daha fazla arabirimin olması durumunda her OLE denetim bir tür kitaplığı olması gerekir.  
  
 Aşağıdaki makroları kendi tür kitaplığı erişimi sağlamak bir OLE denetlemesine izin ver:  
  
### <a name="type-library-access"></a>Tür Kitaplığı Erişimi  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Bildiren bir `GetTypeLib` üye işlevi bir OLE denetiminin (sınıfı bildiriminde kullanılmalıdır).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Implements bir `GetTypeLib` üye işlevi bir OLE denetiminin (sınıfı uygulamasında kullanılmalıdır).|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 Bildirir `GetTypeLib` denetim sınıfınızın üye işlevi.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Tür kitaplığı ilgili denetim sınıfı adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu denetim sınıfı üstbilgi dosyası kullanın.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 Denetimin uygulayan `GetTypeLib` üye işlevi.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Tür kitaplığı ilgili denetim sınıfı adı.  
  
 *tlid*  
 Tür kitaplığı kimliği sayısı.  
  
 `wVerMajor`  
 Tür kitaplığı ana sürüm numarası.  
  
 `wVerMinor`  
 Tür kitaplığı ikincil sürüm numarası.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu kullanan herhangi bir denetim sınıf uygulama dosyada görünmelidir `DECLARE_OLETYPELIB` makrosu.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
   
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
