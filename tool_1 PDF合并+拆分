import os
import fitz
from tqdm import tqdm
import time

def get_all_pdf_files(folder):
    pdf_files = []
    for root, dirs, files in os.walk(folder):
        for file in files:
            if file.endswith('.pdf'):
                pdf_files.append(os.path.join(root, file))
    return pdf_files

# 定义要合并的pdf文件夹路径
pdf_folder = input("定义要合并的pdf文件夹路径: ")
start_time = time.time()

# 获取pdf文件夹下的所有pdf文件名，包括子文件夹中的文件
pdf_files = get_all_pdf_files(pdf_folder)

# 创建一个新的Pdf文件
merged_pdf = fitz.open()

# 依次将每个pdf文件合并到新的Pdf文件中
for filename in tqdm(pdf_files, desc="合并pdf文件", total=len(pdf_files)):
    pdf_doc = fitz.open(filename)
    merged_pdf.insert_pdf(pdf_doc)

# 定义要保存的文件夹路径
output_folder = os.path.join(pdf_folder, '处理后')

# 如果路径不存在，则创建目录
if not os.path.exists(output_folder):
    os.makedirs(output_folder)

# 定义要保存的文件路径
output_path = os.path.join(output_folder, '当前PDF合并.pdf')

# 保存合并后的pdf文件
merged_pdf.save(output_path)

# 关闭所有打开的Pdf文件
merged_pdf.close()

end_time = time.time()
elapsed_time = end_time - start_time
He = f"合并完用时{elapsed_time:.3f}秒。"

# 计时并输出用时
start_time = time.time()

# 定义要拆分的pdf文件路径
pdf_file = os.path.join(output_folder, '当前PDF合并.pdf')

# 创建一个新的文件夹来保存拆分后的文件
output_folder = os.path.join(output_folder, '拆分文件所在地')
if not os.path.exists(output_folder):
    os.makedirs(output_folder)

# 打开pdf文件
pdf_doc = fitz.open(pdf_file)

# 遍历pdf的每一页
for page_idx in tqdm(range(pdf_doc.page_count), desc="拆分pdf文件", total=pdf_doc.page_count):
    # 创建一个新的pdf文档
    new_pdf = fitz.open()
    new_pdf.insert_pdf(pdf_doc, from_page=page_idx, to_page=page_idx)
    # 保存单页pdf文件
    output_file = os.path.join(output_folder, f"page_{page_idx + 1}.pdf")
    new_pdf.save(output_file)
    new_pdf.close()

# 关闭打开的pdf文档
pdf_doc.close()

# 输出用时
end_time = time.time()
elapsed_time = end_time - start_time
Ch = f"拆分用时{elapsed_time:.3f}秒。"
print(He, Ch)

# 这个是让代码继续运行型下去，上面的是让代码第一次运行不需要询问用户是否继续
while True:
    da = input("继续请按回车或者输入 q 退出：")
    daa = "das"
    if da == 'q':
        break
    elif da != '':
        print("无效输入，请重新输入！")
        continue

    # 定义要合并的pdf文件夹路径
    pdf_folder = input("定义要合并的pdf文件夹路径: ")
    start_time = time.time()

    # 获取pdf文件夹下的所有pdf文件名，包括子文件夹中的文件
    pdf_files = get_all_pdf_files(pdf_folder)

    # 创建一个新的Pdf文件
    merged_pdf = fitz.open()

    # 依次将每个pdf文件合并到新的Pdf文件中
    for filename in tqdm(pdf_files, desc="合并pdf文件", total=len(pdf_files)):
        pdf_doc = fitz.open(filename)
        merged_pdf.insert_pdf(pdf_doc)

    # 定义要保存的文件夹路径
    output_folder = os.path.join(pdf_folder, '处理后')

    # 如果路径不存在，则创建目录
    if not os.path.exists(output_folder):
        os.makedirs(output_folder)

    # 定义要保存的文件路径
    output_path = os.path.join(output_folder, '当前PDF合并.pdf')

    # 保存合并后的pdf文件
    merged_pdf.save(output_path)

    # 关闭所有打开的Pdf文件
    merged_pdf.close()

    end_time = time.time()
    elapsed_time = end_time - start_time
    He = f"合并完用时{elapsed_time:.3f}秒。"

    # 计时并输出用时
    start_time = time.time()

    # 定义要拆分的pdf文件路径
    pdf_file = os.path.join(output_folder, '当前PDF合并.pdf')

    # 创建一个新的文件夹来保存拆分后的文件
    output_folder = os.path.join(output_folder, '拆分文件所在地')
    if not os.path.exists(output_folder):
        os.makedirs(output_folder)

    # 打开pdf文件
    pdf_doc = fitz.open(pdf_file)

    # 遍历pdf的每一页
    for page_idx in tqdm(range(pdf_doc.page_count), desc="拆分pdf文件", total=pdf_doc.page_count):
        # 创建一个新的pdf文档
        new_pdf = fitz.open()
        new_pdf.insert_pdf(pdf_doc, from_page=page_idx, to_page=page_idx)
        # 保存单页pdf文件
        output_file = os.path.join(output_folder, f"page_{page_idx + 1}.pdf")
        new_pdf.save(output_file)
        new_pdf.close()

    # 关闭打开的pdf文档
    pdf_doc.close()

    # 输出用时
    end_time = time.time()
    elapsed_time = end_time - start_time
    Ch = f"拆分用时{elapsed_time:.3f}秒。"
    print(He, Ch)
