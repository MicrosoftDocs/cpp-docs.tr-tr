---
title: Makrolar ve genel işlevler için OLE DB Tüketici Şablonları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57f61dd54855a2cf0196c0e269eda92295c818b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33114321"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler
OLE DB Tüketici şablonları aşağıdaki makroları ve genel işlevler şunlardır:  
  
### <a name="global-functions"></a>Genel işlevler  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|Bir hata döndürülürse, OLE DB hata kaydı bilgi döküm aygıta dökümünü yapar.|  
  
### <a name="accessor-map-macros"></a>Erişimci eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)|Erişimci girdiyi başlangıcını işaretler.|  
|[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)|Erişimci eşleme girdilerini başlangıcını işaretler.|  
|[END_ACCESSOR](../../data/oledb/end-accessor.md)|Erişimci girdinin sonuna işaretler.|  
|[END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)|Erişimci eşleme girdilerini sonunu işaretler.|  
  
### <a name="column-map-macros"></a>Sütun eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)|Kullanıcı kayıt sınıfı sütun eşlemesi girdileri başlangıcını işaretler.|  
|[BLOB_ENTRY](../../data/oledb/blob-entry.md)|İkili büyük nesne (BLOB) bağlamak için kullanılır.|  
|[BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)|BLOB veri sütun uzunluğu bildirir.|  
|[BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)|Uzunluğu ve BLOB veri sütunu durumunu raporlar.|  
|[BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)|BLOB veri sütunu durumunu raporlar.|  
|[BLOB_NAME](../../data/oledb/blob-name.md)|İkili büyük nesne sütunu adıyla bağlamak için kullanılır.|  
|[BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)|BLOB veri sütun uzunluğu bildirir.|  
|[BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)|Uzunluğu ve BLOB veri sütunu durumunu raporlar.|  
|[BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)|BLOB veri sütunu durumunu raporlar.|  
|[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)|Yer işareti giriş satır kümesi üzerinde temsil eder. Özel türde bir sütun girişi bir yer işareti giriştir.|  
|[COLUMN_ENTRY](../../data/oledb/column-entry.md)|Bağlama veritabanında belirli bir sütuna temsil eder.|  
|[COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler `type`, *uzunluğu*, *duyarlık*, `scale`, ve *durum* parametreleri.|  
|[COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler *uzunluğu* değişkeni.|  
|[COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler *durum* ve *uzunluğu* parametreleri.|  
|[COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler *duyarlık* ve `scale` parametreleri.|  
|[COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler *uzunluğu* değişkeni *duyarlık* ve `scale` parametreleri.|  
|[COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler *durum* ve *uzunluğu* değişkenleri *duyarlık* ve `scale` parametreleri.|  
|[COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler *durum* değişkeni *duyarlık* ve `scale` parametreleri.|  
|[COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler *durum* değişkeni.|  
|[COLUMN_ENTRY_TYPE](../../data/oledb/column-entry-type.md)|Bağlama veritabanında belirli bir sütuna temsil eder. Destekler `type` parametresi.|  
|[COLUMN_ENTRY_TYPE_SIZE](../../data/oledb/column-entry-type-size.md)|Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler `type` ve `size` parametreleri.|  
|[COLUMN_NAME](../../data/oledb/column-name.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder.|  
|[COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Veri türü, boyutu, duyarlık, Ölçek, sütun uzunluğu ve sütun durum belirtimi destekler.|  
|[COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Sütun uzunluğu belirtimi destekler.|  
|[COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Sütun uzunluğu ve durum belirtimi destekler.|  
|[COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Kesinlik ve ölçek belirtimi destekler.|  
|[COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Duyarlık ve ölçek sütun uzunluğu belirtimi destekler.|  
|[COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Duyarlık, Ölçek, sütun uzunluğu ve sütun durum belirtimi destekler.|  
|[COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Duyarlık ve ölçek sütun durum belirtimi destekler.|  
|[COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Sütun durum belirtimi destekler.|  
|[COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Veri türü belirtimi destekler.|  
|[COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Veri türü, duyarlık ve ölçek belirtimi destekler.|  
|[COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Veri türü ve boyutunu belirtimi destekler.|  
|[COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)|Belirli bir veritabanı sütununa bir bağlama tarafından adını temsil eder. Veri türü ve sütun durumu belirtimi destekler.|  
|[END_COLUMN_MAP](../../data/oledb/end-column-map.md)|Sütun eşlemesi girişleri sonunu işaretler.|  
  
### <a name="command-macros"></a>Komut makroları  
  
|||  
|-|-|  
|[DEFINE_COMMAND](../../data/oledb/define-command.md)|Satır kümesi kullanırken oluşturmak için kullanılan komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. Yalnızca belirtilen uygulama türü (ANSI veya Unicode) eşleşen dize türlerini kabul eder. Kullanmanız önerilir [defıne_command_ex](../../data/oledb/define-command-ex.md) yerine `DEFINE_COMMAND`.|  
|[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)|Satır kümesi kullanırken oluşturmak için kullanılan komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. ANSI ve Unicode uygulamaları destekler.|  
  
### <a name="parameter-map-macros"></a>Parametre eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)|Kullanıcı kayıt sınıfı parametre eşleme girdileri başlangıcını işaretler.|  
|[END_PARAM_MAP](../../data/oledb/end-param-map.md)|Parametre eşleme girdilerini sonunu işaretler.|  
|[SET_PARAM_TYPE](../../data/oledb/set-param-type.md)|Belirtir `COLUMN_ENTRY` izleyin makroları `SET_PARAM_TYPE` makrosu giriş, çıkış veya giriş/çıkış olarak.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)