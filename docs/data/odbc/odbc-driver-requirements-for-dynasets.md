---
title: Dynaset'ler için ODBC sürücü gereksinimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9fad26440cea2c8ec2efd7d07dacb83547252e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089239"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>Dynaset'ler için ODBC Sürücü Gereksinimleri
MFC ODBC veritabanı sınıfları dinamik kümeler kayıt kümeleri dinamik özelliklere sahip olan; Bunlar belirli şekillerde veri kaynağı ile eşitlenmiş olarak kalır. Düzey 2 API uygunluğu ile bir ODBC sürücüsü MFC dinamik kümeler (ancak değil salt iletme kayıt kümeleri) gerektirir. Varsa sürücüsü, [veri kaynağı](../../data/odbc/data-source-odbc.md) düzey 1 API için uyumlu ayarlanırsa, hem güncelleştirilebilir ve salt okunur anlık görüntüler ve salt iletme kayıt kümeleri, ancak dinamik kümeleri kullanmaya devam edebilirsiniz. Ancak, genişletilmiş getirme ve anahtar kümesi temelli imleçler destekliyorsa, düzey 1 sürücüsü dinamik kümeleri destekleyebilir.  
  
 ODBC terminolojisinde dinamik kümeler ve anlık görüntüleri için işaretçiler olarak adlandırılır. İmleç, bir kayıt kümesi içindeki konumunu izlemek için kullanılan bir düzenektir. Dynasets için sürücü gereksinimleri hakkında daha fazla bilgi için bkz: [Dynaset](../../data/odbc/dynaset.md). İmleçler hakkında daha fazla bilgi için bkz: [açık veritabanı bağlantısı (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) MSDN belgelerine SDK'da.  
  
> [!NOTE]
>  Güncelleştirilebilir kayıt kümeleri için ODBC sürücüsü ya da konumlandırılmış güncelleştirme deyimleri desteklemesi gerekir veya **:: SQLSetPos** ODBC API işlevi. Her ikisi de destekleniyorsa, MFC kullanan **:: SQLSetPos** verimlilik. Alternatif olarak, anlık görüntüler için güncelleştirilebilir için anlık görüntüler (statik imleçler ve konumlandırılmış güncelleştirme deyimleri) gerekli desteği sağlayan imleç kitaplığı kullanabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC Temelleri](../../data/odbc/odbc-basics.md)