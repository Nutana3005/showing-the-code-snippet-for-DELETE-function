# showing-the-code-snippet-for-DELETE-function
@app.route("/products/<int:id>", methods=["DELETE"])
def delete_product(id):
    product = Product.find(id)
    if product:
        product.delete()
        return "", 204
    return {"error": "Product not found"}, 404
