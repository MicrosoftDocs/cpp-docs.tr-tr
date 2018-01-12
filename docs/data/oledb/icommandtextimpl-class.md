---
title: "Icommandtextımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ICommandText
dev_langs: C++
helpviewer_keywords: ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 53b5e19fbeaccfb61380054426315ad9b92f624a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl Sınıfı
Bir uygulamasını sağlar [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Komut sınıfı türetilmiş **Icommandtextımpl**.  
  
## <a name="members"></a>Üyeler  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|Son çağrı tarafından ayarlanan metin komutu döndürür [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|Varolan komut metni değiştirme komut metni ayarlar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|Komut metni depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Zorunlu bir arabirim açma komutları.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** altdb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)