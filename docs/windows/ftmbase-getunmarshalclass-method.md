---
title: FtmBase::GetUnmarshalClass metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs:
- C++
helpviewer_keywords:
- GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 329d43227aa131728db72086f99cb86797a5e1e3
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571158"
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass Metodu
COM kodu için karşılık gelen proxy içeren DLL bulmak için kullandığı CLSID değerini alır. COM proxy'si başlatılmamış bir örneğini oluşturmak için bu DLL'yi yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
### <a name="parameters"></a>Parametreler  
 *riid*  
 Sıralanması arabirimi tanımlayıcısını başvuru.  
  
 *BD*  
 Sıralanması arabirim işaretçisi; çağıranın istendiği arayüz işaretçisi yoksa NULL olabilir.  
  
 *dwDestContext*  
 Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.  
  
 Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.  
  
 Unmarshaling ya da geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.  
  
 *pvDestContext*  
 Gelecekte kullanılmak üzere ayrılmış; NULL olmalıdır.  
  
 *mshlflags*  
 Bu işlem tamamlandığında CLSID istemci işlemini bir ara sunucu oluşturmak için kullanılacak işaretçi.  
  
 *Pcıd*  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, S_FALSE.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase Sınıfı](../windows/ftmbase-class.md)