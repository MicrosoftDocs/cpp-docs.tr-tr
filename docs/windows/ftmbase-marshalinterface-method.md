---
title: Ftmbase::marshalınterface metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23779cbe0b27680122c6aa3a8f8748c39f28078e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647413"
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface Metodu
Bir akışa bir proxy nesnesi içinde bazı istemci işlemini başlatmak için gerekli verileri yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pStm*  
 Hazırlama sırasında kullanılmak üzere stream işaretçisi.  
  
 *riid*  
 Sıralanması arabirimi tanımlayıcısını başvuru. Bu arabirim nesnesinden türetilmesi `IUnknown` arabirimi.  
  
 *BD*  
 İşaretçi sıralanması arabirim işaretçisi için; çağıranın istendiği arayüz işaretçisi yoksa NULL olabilir.  
  
 *dwDestContext*  
 Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.  
  
 Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.  
  
 Unmarshaling, geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.  
  
 *pvDestContext*  
 Gelecekte kullanılmak üzere ayrılmış; sıfır olmalıdır.  
  
 *mshlflags*  
 İstemci işlemine aktarılacak veri sıralanması olup olmadığını belirtir: genellikle bu durum — burada da alınabilir birden çok istemci tarafından genel bir tablo yazılamaz veya okunamaz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK  
 Arabirim işaretçisi başarılı bir şekilde sıralanır.  
  
 E_NOINTERFACE  
 Belirtilen bir arabirim desteklenmiyor.  
  
 STG_E_MEDIUMFULL  
 Akış dolu.  
  
 E_FAIL  
 İşlem başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase Sınıfı](../windows/ftmbase-class.md)