---
title: CDataSource::OpenFromInitializationString | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
dev_langs:
- C++
helpviewer_keywords:
- OpenFromInitializationString method
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dac964f7c6c863f85769a164fab8c418e1c45430
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090940"
---
# <a name="cdatasourceopenfrominitializationstring"></a>CDataSource::OpenFromInitializationString
Kullanıcı tarafından sağlanan başlatma dizesi tarafından belirtilen bir veri kaynağı açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,   
   bool fPromptForInfo= false) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *szInitializationString*  
 [in] Başlatma dizesi.  
  
 *fPromptForInfo*  
 [in] Bu bağımsız değişken ayarlanmışsa **true**, ardından `OpenFromInitializationString` ayarlayacaksınız **DBPROP_INIT_PROMPT** özelliğine **DBPROMPT_COMPLETEREQUIRED**, kullanıcının olmasını belirtir yalnızca daha fazla bilgi gerekirse istenir. Başlatma dizesinin bir parola gerektiren bir veritabanını belirtir durumlarda yararlıdır, ancak dize parola içermiyor. Kullanıcıdan bir parola (veya diğer eksik bilgileri) istenir veritabanına bağlanmaya çalışırken.  
  
 Varsayılan değer **false**, kullanıcı asla sorulması belirtir (ayarlar **DBPROP_INIT_PROMPT** için **DBPROMPT_NOPROMPT**).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem oledb32.dll içinde hizmet Bileşenleri'ni kullanarak bir veri kaynağı nesnesi açar; Bu DLL kaynak havuzu, otomatik işlem kaydı vb. gibi hizmet bileşenleri özellikleri uygulamasını içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataSource Sınıfı](../../data/oledb/cdatasource-class.md)