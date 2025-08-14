from flask import Flask, render_template, request, redirect, url_for
from flask_sqlalchemy import SQLAlchemy
import os

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///users.db'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
db = SQLAlchemy(app)

# Model
class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(100), nullable=False)
    email = db.Column(db.String(120), nullable=False)

# Home - Read
@app.route('/')
def index():
    users = User.query.all()
    return render_template('index.html', users=users)

# Create - Add new user
@app.route('/add', methods=['GET', 'POST'])
def add():
    if request.method == 'POST':
        name = request.form['name']
        email = request.form['email']
        if name and email:
            new_user = User(name=name, email=email)
            db.session.add(new_user)
            db.session.commit()
            return redirect(url_for('index'))
    return render_template('add.html')

# Update - Edit user
@app.route('/edit/<int:id>', methods=['GET', 'POST'])
def edit(id):
    user = User.query.get_or_404(id)
    if request.method == 'POST':
        user.name = request.form['name']
        user.email = request.form['email']
        db.session.commit()
        return redirect(url_for('index'))
    return render_template('edit.html', user=user)

# Delete user
@app.route('/delete/<int:id>')
def delete(id):
    user = User.query.get_or_404(id)
    db.session.delete(user)
    db.session.commit()
    return redirect(url_for('index'))

if __name__ == '__main__':
    if not os.path.exists('users.db'):
        db.create_all()
    app.run(debug=True)
