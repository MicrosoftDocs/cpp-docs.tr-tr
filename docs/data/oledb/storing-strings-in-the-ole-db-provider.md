---
title: "Dizeleri OLE DB Sağlayıcısında Depolama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 018bf17cbd4106b4b76ec58ab524d8da6f14b62d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Dizeleri OLE DB Sağlayıcısında Depolama
MyProviderRS.h öğesinde ATL OLE DB Sağlayıcı Sihirbazı adlı varsayılan kullanıcı kaydı oluşturur `CWindowsFile`. İki dizeyi işlemek için ya da değiştirme `CWindowsFile` veya kendi kullanıcı kaydı aşağıdaki kodda gösterildiği gibi ekleyin:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 Veri üyeleri `szCommand` ve `szText` ile iki dizeyi temsil eden `szCommand2` ve `szText2` gerekirse ek sütunlar sağlama. Veri üyesi `dwBookmark` bu basit salt okunur sağlayıcı için gerekli değildir, ancak daha sonra eklemek için kullanılan bir `IRowsetLocate` arabirim; bkz [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==` İşleci örnekleri karşılaştırır (Bu işleci uygulamak isteğe bağlı).  
  
 Bu yapıldığında, sağlayıcınız derlemek ve çalıştırmak hazır olmanız gerekir. Sağlayıcı test etmek için eşleşen işlevselliğe sahip bir tüketici gerekir. [Basit Tüketici Uygulama](../../data/oledb/implementing-a-simple-consumer.md) böyle bir test tüketicisinin oluşturulacağını gösterir. Test tüketici sağlayıcı ile çalıştırın. ' I tıklattığınızda test tüketici uygun dizeleri sağlayıcıdan alır olduğunu doğrulayın **çalıştırmak** düğmesini **Test Tüketicisi** iletişim kutusu.  
  
 Sağlayıcınıza başarıyla Test ettiğinizde, ek arabirimler uygulayarak işlevselliğini artırmak isteyebilirsiniz. Bir örnek gösterilen [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Basit Salt Okunur Sağlayıcıyı Uygulama](../../data/oledb/implementing-the-simple-read-only-provider.md)