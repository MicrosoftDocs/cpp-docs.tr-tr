---
title: Dizeleri OLE DB Sağlayıcısında Depolama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75f845027e5c629fe61b8cca6ab3f23306aa57bf
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053233"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Dizeleri OLE DB Sağlayıcısında Depolama

CustomRS.h içinde ATL OLE DB sağlayıcısı Sihirbazı adlı bir varsayılan kullanıcı kayıt oluşturur. `CWindowsFile`. İki dizenin işlemek için ya da değiştirme `CWindowsFile` veya kendi kullanıcı kaydı aşağıdaki kodda gösterildiği gibi ekleyin:

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

Veri üyeleri `szCommand` ve `szText` ile iki dizeyi temsil eden `szCommand2` ve `szText2` gerekirse ek sütunlar sağlama. Veri üyesi `dwBookmark` bu basit bir salt okunur sağlayıcı için gerekli değildir, ancak daha sonra eklemek için kullanılan bir `IRowsetLocate` arabirim; bkz [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==` İşleci örnekleri karşılaştırır (Bu imlecini uygulamadan isteğe bağlı).

Sağlayıcınıza bu yapıldığında, derlemek ve çalıştırmak hazır olması gerekir. Sağlayıcıyı test eşleşen işlevselliğe sahip bir tüketici gerekir. [Basit Tüketici Uygulama](../../data/oledb/implementing-a-simple-consumer.md) bu tür bir test tüketici oluşturma işlemi gösterilmektedir. Test tüketici, sağlayıcı ile çalıştırın. Test tüketici tıkladığınızda sağlayıcısından uygun dizelerden görüntüleyip getirdiğini doğrulayın **çalıştırma** düğmesine **Test tüketici** iletişim kutusu.

Sağlayıcınız başarıyla sınadığınızda ek arabirimlerini uygulayarak işlevselliğini artırmak isteyebilirsiniz. Bir örnek gösterilmiştir [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Basit Salt Okunur Sağlayıcıyı Uygulama](../../data/oledb/implementing-the-simple-read-only-provider.md)