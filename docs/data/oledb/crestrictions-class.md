---
description: 'Daha fazla bilgi edinin: CRestrictions Sınıfı'
title: CRestrictions Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
ms.openlocfilehash: 28eee2ea8d7e3b28edaab745c48426c878cc2f2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170288"
---
# <a name="crestrictions-class"></a>CRestrictions Sınıfı

Şema satır kümeleri için kısıtlamalar belirtmenize olanak sağlayan bir genel sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, short nRestrictions, const GUID* pguid>
class CRestrictions :
   public CSchemaRowset <T, nRestrictions>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Erişimci için kullanılan sınıf.

*Nkısıtlamalar*<br/>
Şema satır kümesi için kısıtlama sütunlarının sayısı.

*PGUID*<br/>
Şemanın GUID 'sine yönelik bir işaretçi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldbsch. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[Aç](#open)|Kullanıcı tarafından sağlanan kısıtlamalara göre bir sonuç kümesi döndürür.|

## <a name="crestrictionsopen"></a><a name="open"></a> CRestrictions:: Open

Kullanıcı tarafından sağlanan kısıtlamalara göre bir sonuç kümesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(const CSession& session,
   LPCTSTR lpszParam 1 = NULL,
   LPCTSTR lpszParam 2 = NULL,
   LPCTSTR lpszParam 3 = NULL,
   LPCTSTR lpszParam 4 = NULL,
   LPCTSTR lpszParam 5 = NULL,
   LPCTSTR lpszParam 6 = NULL,
   LPCTSTR lpszParam 7 = NULL,
   bool bBind = true);
```

#### <a name="parameters"></a>Parametreler

*oturumuna*<br/>
'ndaki Veri kaynağına bağlanmak için kullanılan mevcut bir oturum nesnesini belirtir.

*lpszParam*<br/>
'ndaki Şema satır kümesi üzerindeki kısıtlamaları belirtir.

*bBind*<br/>
'ndaki Sütun eşlemesinin otomatik olarak bağlanıp bağlanmayacağını belirtir. Varsayılan değer **`true`** , sütun eşlemesinin otomatik olarak bağlanmasına neden olur. *BBind* 'in ayarlanması, **`false`** el ile bağlayabilmeniz için sütun eşlemesinin otomatik bağlamasını engeller. (El ile bağlama, OLAP kullanıcılarına özellikle ilgi çekici bir şekilde yapılır.)

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bir şema satır kümesinde en fazla yedi kısıtlama belirtebilirsiniz.

Her şema satır kümesinde tanımlı kısıtlamalar hakkında bilgi için bkz. [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Şema satır kümesi sınıfları ve typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)
